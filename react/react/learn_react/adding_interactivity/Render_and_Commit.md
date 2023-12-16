
리액트는 Trigger, Render, Commit의 세단계를 거친다.


1. Trigger(a Render)
컴포넌트의 첫번째 Render이거나, state가 업데이트되었을경우에
render가 trigger 된다.


2. Render

화면에 표시되어야하는 Component를 호출한다.

첫번째 Render: Root Component를 Render한다
이후의 Render: Render가 촉진된 컴포넌트들을 Render한다.


3. Commit  (changes to the dom)