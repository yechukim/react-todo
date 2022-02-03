# react to-do

사용된 라이브러리
- react-icons
- styled-components

## 1.컴포넌트 만들기
`styled-components`

- 글로벌 스타일 추가하기: `createGlobalStyles`
- 컴포넌트 셀렉터 : 해당 블럭위에 커서가 있으면 `Remove` 컴포넌트를 보여줘 
```js
const TodoItemBlock = styled.div`
  display: flex;
  align-items: center;
  padding-top: 12px;
  padding-bottom: 12px;
  &:hover {
    ${Remove} {
      display: initial;
    }
  }
`;
```
- `overflow-y` CSS property 
sets what shows when content overflows a block-level element's top and bottom edges. This may be nothing, a scroll bar, or the overflow content.\
`auto`로 하면 해당 블럭을 넘어가면 스크롤바가 생김 

## 2. 상태관리
`Context API`

- state, dispatch Context를 따로 만들면 dispatch만 필요한 컴포넌트에서 불필요한 렌더링을 방지할 수 있다 
- TodoItem, TodoCreate 을 `React.memo()`로 감싸서 최적화해줌 
- context custom hook 만들때 해딩 context provider 내부에서 사용해야 오류가 없는데, 실수 방지를 위해 context가 없을 때 오류가 나도록 설정해주는 것이 좋다. -- `TodoContext.js` 참고