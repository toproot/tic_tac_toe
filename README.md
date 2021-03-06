# ๐ React๋ก ๋ง๋๋ Tic Tac Toe
> :bulb: React ๊ณต์ ํํ์ด์ง์ ํํ ๋ฆฌ์ผ์ ๋ฐ๋ผ์ ์ฝ๋ฉ์ ํด๋ด์ผ๋ก์จ ๊ธฐ๋ณธ์ ์ธ ๊ธฐ๋ฅ ๊ตฌํ์ ์ตํ



> ๋ชฉ์ฐจ

[toc]

---





## ๐ ๋ชฉํ : React ๊ณต์๋ฌธ์๋ฅผ ์ฐธ๊ณ ํ์ฌ Tic-Tac-Toe ๊ฒ์ ๊ตฌํ





### 1. ๊ธฐ๋ณธ๊ตฌ์กฐ

- ์ด๊ธฐ์ฝ๋๋ ๊ณต์๋ฌธ์์์ ์ ๊ณต
- index.js๋ 3๊ฐ์ ํด๋์ค๋ก ๊ตฌ์ฑ
  - Square
  - Board
  - Game



![image-20210702100616482](README/image-20210702100616482.png)





---





### 2. Props๋ฅผ ํตํด ๋ฐ์ดํฐ ์ ๋ฌํ๊ธฐ



>  :bulb: ๋ถ๋ชจ Board ์ปดํฌ๋ํธ์์ ์์ Square ์ปดํฌ๋ํธ๋ก "prop" ์ ๋ฌ.



- Board

```react
class Board extends React.Component {
  renderSquare(i) {
    return <Square value={i} />;
  }
```

- Square

```react
class Square extends React.Component {
  render() {
    return (
      <button className="square">
        {this.props.value}
      </button>
    );
  }
}
```



![image-20210702101411043](README/image-20210702101411043.png)



---







### 3. ์ฌ์ฉ์์ ์ํธ์์ฉํ๋ ์ปดํฌ๋ํธ ๋ง๋ค๊ธฐ



> :bulb:  ํ์ดํํจ์๋ฅผ ์ด์ฉํ์ฌ Square์ ํด๋ฆญํจ์ ์ ์ฉ.

- ์ฃผ์โ๏ธ: ํ์ดํ ํจ์์์ "() =>" ์ ๋ฃ์ด์ฃผ์ง ์์ผ๋ฉด ์ปดํฌ๋ํธ๊ฐ ๋ค์ ๋ ๋๋ง ๋ ๋ ๋ง๋ค ๊ฒฝ๊ณ ์ฐฝ์ ๋์ฐ๊ฒ ๋จ!!

  

![image-20210702101645045](README/image-20210702101645045.png)







> :bulb:  ํด๋ฆญํ  ๋ X ๋ก ๊ฐ์ด ๋ณ๊ฒฝ๋  ์ ์๋๋ก ๊ตฌํ

- ์ฃผ์โ๏ธ : ๋ชจ๋  React ์ปดํฌ๋ํธ ํด๋์ค๋ `์์ฑ์`๋ฅผ ๊ฐ์ง ๋ `super(props)` ํธ์ถ ๊ตฌ๋ฌธ๋ถํฐ ์์ฑํด์ผ ํฉ๋๋ค.



- Squareํด๋์ค์ ์๋ก์ด ์์ฑ์ ๋ง๋ค๊ธฐ

  ```react
    constructor(props) {
      super(props);
      this.state = {
        value: null,
      };
    }
  ```



- button ํ๊ทธ์ onClick ํจ์ ์์ .
  - ํด๋ฆญํ์ ๋ ๊ธฐ์กด ์์ฑ์์ธ state์ ๊ฐ์ด 'X'๋ก ๋ฐ๋ ์ ์๋๋ก.



![image-20210702102447345](README/image-20210702102447345.png)

---





### 4. ๊ฐ๋ฐ์ ๋๊ตฌ

> :bulb: React Devtools ๊ตฌ๊ธ ํฌ๋กฌ ํ์ฅ ํ๋ก๊ทธ๋จ ์ค์น



![image-20210702103126114](README/image-20210702103126114.png)



![image-20210702103404391](README/image-20210702103404391.png)



![image-20210702103324093](README/image-20210702103324093.png)





---





### 5. ๊ฒ์ ์์ฑํ๊ธฐ



- ์น์๋ฅผ ํ์ธํ๊ธฐ ์ํด ์ฌ๋ฌ๊ฐ์ ์์ ์ปดํฌ๋ํธ๋ค์ ๋ถ๋ชจ์ปดํฌ๋ํธ์ ๊ณต์  state๋ฅผ ์ ์
- ๋ถ๋ชจ ์ปดํฌ๋ํธ๋ props๋ฅผ ์ฌ์ฉํ์ฌ ์์ ์ปดํฌ๋ํธ์ state๋ฅผ ๋ค์ ์ ๋ฌ ๊ฐ๋ฅ
- ์ด๋ฌํ ๋ฐฉ๋ฒ์ผ๋ก ์์ ์ปดํฌ๋ํธ๋ค์ด ์๋ก ๋๋ ๋ถ๋ชจ ์ปดํฌ๋ํธ์ ๋๊ธฐํ ํ๋๋ก ํจ.



- Board์ ์์ฑ์ ์ถ๊ฐํ๊ณ  9๊ฐ์ ์ฌ๊ฐํ์ ํด๋นํ๋ 9๊ฐ์ null ๋ฐฐ์ด์ ์ด๊ธฐ state๋ก ์ค์ 

  ```react
    constructor(props) {
      super(props);
      this.state = {
        squares: Array(9).fill(null),
      };
    }
  ```

  

- ๊ธฐ์กด์๋ Square์ ์์ฒด state์ ๋ฐ๋ผ 'X' ํ์๋ก ๋ฐ๊พธ๊ณ  ์์์.

- ๊ทธ๋์ Square๋ Board์์ ์ ๋ฌํ๋ valeu prop์ ๋ฌด์ํ ์ํฉ

- Prop ์ ๋ฌ๋ฐฉ๋ฒ์ ๋ค์ ์ฌ์ฉํ๊ธฐ ์ํด Board์ renderSquare๋ฅผ ๋ค์๊ณผ ๊ฐ์ด ์์ .

  ```react
    renderSquare(i) {
      return <Square value={this.state.squares[i]} />;
    }
  ```



- Square๋ ์ด์  ๋น ์ฌ๊ฐํ์ 'X', 'O', ๋๋ null์ธ value prop์ ๋ฐ์.

- ๋ค์์ผ๋ก Square๋ฅผ ํด๋ฆญํ  ๋ Board์ ํจ์๋ฅผ ํธ์ถํ์ฌ ๊ฐ์ ์ฑ์์ฃผ๊ธฐ ์ํด ๋ค์๊ณผ ๊ฐ์ด ์์ .

  ```react
    renderSquare(i) {
      return (
        <Square
          value={this.state.squares[i]}
          onClick={() => this.handleClick(i)}
        />
      );
    }
  ```

  



- Square

  ```react
  class Square extends React.Component {
    constructor(props) {
      super(props);
      this.state = {
        value: null,
      };
    }
  
    render() {
      return (
        <button 
          className="square"
          onClick={() => this.props.onClick()}
        >
          {this.props.value}
        </button>
      );
    }
  }
  ```

- Board

  ```react
  class Board extends React.Component {
    constructor(props) {
      super(props);
      this.state = {
        squares: Array(9).fill(null),
      };
    }
    handleClick(i) {
      const squares = this.state.squares.slice();
      squares[i] = 'X';
      this.setState({squares: squares});
    }
    
    renderSquare(i) {
      return (
        <Square 
          value={this.state.squares[i]}
          onClick={() => this.handleClick(i)}
        />
      );
    }
  ```







> :bulb:  ํ์ฌ๊น์ง ์ ๋ฆฌ



- ๊ฐ ์ฌ๊ฐํ์ state๊ฐ Board ์ปดํฌ๋ํธ์ ์ ์ฅ.
- Board์ ์ํ๊ฐ ๋ณํ๋ฉด Square ์ปดํฌ๋ํธ๋ ์๋ ๋ ๋๋ง
- Board ์ปดํฌ๋ํธ์ ๋ชจ๋  ์ฌ๊ฐํ์ ์ํ๋ฅผ ์ ์งํ๋ ๊ฒ์ผ๋ก ์ดํ์ ์น์๋ฅผ ๊ฒฐ์  ๊ฐ๋ฅ
- Square ์ปดํฌ๋ํธ๋ ๋์ด์ state๋ฅผ ์ ์งํ์ง ์๊ธฐ ๋๋ฌธ์ Board ์ปดํฌ๋ํธ์ ๊ฐ์ ๋ฐ๊ณ , ์ ๋ณด ์ ๋ฌ
- Board๋ ์ด์  Sqaure๋ฅผ ์์ ํ ์ ์ดํ๋ฏ๋ก ์ด๋ฌํ ๊ฒ์ react์ฉ์ด๋ก **์ ์ด๋๋ ์ปดํฌ๋ํธ** ๋ผ๊ณ  ํจ.

![image-20210702110311331](README/image-20210702110311331.png)







---



### 6. ํจ์ ์ปดํฌ๋ํธ



- ๊ธฐ์กด์ ์์ฑํ๋ Squareํด๋์ค๋ฅผ props๋ฅผ ์๋ ฅ๋ฐ์์ ๋ ๋๋งํ  ๋์์ ๋ฐํํ๋ ํจ์๋ก ์์ฑ
- ํด๋์ค๋ก ์์ฑํ๋ ๊ฒ๋ณด๋ค ๋น ๋ฅด๊ฒ ์์ฑํ  ์ ์๊ณ , ๋ง์ ์ปดํฌ๋ํธ๋ฅผ ํจ์ ์ปดํฌ๋ํธ๋ก ํํ ๊ฐ๋ฅ



```react
function Square(props) {
  return (
    <button className="square" onClick={props.onClick}>
      {props.value}
    </button>
  )
}
```





---





### 7. ์์ ๋ง๋ค๊ธฐ



- ๊ฒ์ํ์ ํ์ฌ 'X'๋ง ๋ํ๋๊ณ  ์๋๋ฐ "O"๋ฅผ ํ์๋๋๋ก ์์ 
- ๋จผ์  ์์ฑ์์ xIsNext๋ฅผ ์ถ๊ฐํด์ฃผ๊ณ  handleClick์ผ๋ก "X", "O"๊ฐ ๋ฒ๊ฐ์๊ฐ๋ฉด์ ๋ํ๋๋๋ก ๊ตฌํ.



![image-20210702111141534](README/image-20210702111141534.png)



- Board์ `render` ์์ ์๋ โstatusโ ํ์คํธ๋ ๋ฐ๊ฟ์ ์ด๋ ํ๋ ์ด์ด๊ฐ ๋ค์ ์ฐจ๋ก์ธ์ง ์ถ๋ ฅ

  ```react
    render() {
      const status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
  ```

  



---







### 8. ์น์ ๊ฒฐ์ ํ๊ธฐ



- ์น๋ถ๊ฐ ๋๋ ๋์ ๋์ด์ ๋ ๊ณณ์ด ์์ ๋๋ฅผ ์๋ ค์ฃผ์ด ์น๋ถ ๊ฒฐ์ ํ๊ธฐ

- 9๊ฐ์ ์ฌ๊ฐํ ๋ฐฐ์ด์ ๊ฐ์ง๊ณ  ํจ์๋ ์น์๋ฅผ ํ์ธํ์ฌ ์ ์ ํ ๊ฐ์ผ๋ก 'X', 'O' ๋๋ null์ ๋ฐํ.

  ```react
  function calculateWinner(squares) {
    const lines = [
      [0, 1, 2],
      [3, 4, 5],
      [6, 7, 8],
      [0, 3, 6],
      [1, 4, 7],
      [2, 5, 8],
      [0, 4, 8],
      [2, 4, 6],
    ];
    for (let i = 0; i < lines.length; i++) {
      const [a, b, c] = lines[i];
      if (squares[a] && squares[a] === squares[b] && squares[a] === squares[c]) {
        return squares[a];
      }
    }
    return null;
  }
  ```



- ์ด๋ค ํ๋ ์ด์ด๊ฐ ์ฐ์นํ๋์ง ํ์ธํ๊ธฐ ์ํด Board์ render ํจ์์์ calcuateWinner(squares) ํธ์ถ

  ```react
      const winner = calculateWinner(this.state.squares);
      let status;
      if (winner) {
        status = 'Winner: ' + winner;
      } else {
        status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
      }
  ```

- ๋๊ตฐ๊ฐ๊ฐ ์น๋ฆฌํ๊ฑฐ๋ ์ด๋ฏธ Square๊ฐ ์ฑ์์ ธ ์๋ ์ํฉ์์๋ handleClick ํจ์๊ฐ ๋ฌด์๋๋๋ก ๋ณ๊ฒฝ

  ```react
      if (calculateWinner(squares) || squares[i]) {
        return;
      }
  ```



![image-20210702112012441](README/image-20210702112012441.png)





---



### 9. ์๊ฐ ์ฌํ ์ถ๊ฐํ๊ธฐ



> :bulb: ๋์์ ๋ํ ๊ธฐ๋ก ์ ์ฅํ๊ธฐ



- ๊ณต์๋ฌธ์ "๋ถ๋ณ์ฑ"

  https://ko.reactjs.org/tutorial/tutorial.html#why-immutability-is-important



- Slice()๋ฅผ ์ฌ์ฉํด ๋งค ๋์ ์ดํ์ square์ ์๋ก์ด ๋ณต์ฌ๋ณธ์ ๋ถ๋ณ๊ฐ์ฒด๋ก ์ทจ๊ธํ์ฌ History ๋ฐฐ์ด์ ์ ์ฅ





> :bulb: ๋ค์ State ๋์ด์ฌ๋ฆฌ๊ธฐ

- Game ํด๋์ค ๋ด ์์ฑ์ ์์ฑ

  ```react
  class Game extends React.Component {
    constructor(props) {
      super(props);
      this.state = {
        history: [{
          squares: Array(9).fill(null),
        }],
        xIsNext: true,
      };
    }
  ```

- Game ์ปดํฌ๋ํธ์์ Board์ปดํฌ๋ํธ๋ก squares์ onClick poprs๋ฅผ ์ ๋ฌํ๊ธฐ ์ํด Board ์ปดํฌ๋ํธ return ์์ 

  ```react
  value={this.props.squares[i]}
  onClick={() => this.props.onClick(i)}
  ```

- Game ์ปดํฌ๋ํธ์ `render` ํจ์๋ฅผ ๊ฐ์ฅ ์ต๊ทผ ๊ธฐ๋ก์ ์ฌ์ฉํ๋๋ก ์๋ฐ์ดํธํ์ฌ ๊ฒ์์ ์ํ๋ฅผ ํ์ธํ๊ณ  ํ์

  ```react
    render() {
      const history = this.state.history;
      const current = history[history.length - 1];
      const winner = calculateWinner(current.squares);
      let status;
      if (winner) {
        status = 'Winner: ' + winner;
      } else {
        status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
      }
  
      return (
        <div className="game">
          <div className="game-board">
            <Board
              squares={current.squares}
              onClick={(i) => this.handleClick(i)}
            />
          </div>
          <div className="game-info">
            <div>{status}</div>
            <ol>{/* TODO */}</ol>
          </div>
        </div>
      );
    }
  ```

- Game ์ปดํฌ๋ํธ์ `render` ํจ์๋ฅผ ๊ฐ์ฅ ์ต๊ทผ ๊ธฐ๋ก์ ์ฌ์ฉํ๋๋ก ์๋ฐ์ดํธํ์ฌ ๊ฒ์์ ์ํ๋ฅผ ํ์ธํ๊ณ  ํ์ํ๊ฒ ์ต๋๋ค.

  ```react
   render() {
      const history = this.state.history;
      const current = history[history.length - 1];
      const winner = calculateWinner(current.squares);
      let status;
      if (winner) {
        status = 'Winner: ' + winner;
      } else {
        status = 'Next player: ' + (this.state.xIsNext ? 'X' : 'O');
      }
  
      return (
        <div className="game">
          <div className="game-board">
            <Board
              squares={current.squares}
              onClick={(i) => this.handleClick(i)}
            />
          </div>
          <div className="game-info">
            <div>{status}</div>
            <ol>{/* TODO */}</ol>
          </div>
        </div>
      );
    }
  ```

  

- Board์ handleClick ํจ์๋ฅผ Game์ผ๋ก ์ฎ๊ฒจ์ฃผ๊ณ  render์ ์ค๋ณต๋๋ ์ฝ๋๋ฅผ ์ ๊ฑฐํด์ค๋๋ค.





> :bulb: ๊ณผ๊ฑฐ์ ์ด๋ ํ์ํ๊ธฐ



- JS์ map() ํจ์๋ฅผ ๊ฐ์ง๊ณ  ํด๋ฆญํ ๊ธฐ๋ก์ ๋จ๊ฒจ์ฃผ๋ history๋ฅผ map ํ๊ธฐ

  ```react
      const moves = history.map((step, move) => {
        const desc = move ?
          'Go to move #' + move :
          'Go to game start';
        return (
          <li>
            <button onClick={() => this.jumpTo(move)}>{desc}</button>
          </li>
        );
      });
  ```

  ![image-20210702113935513](README/image-20210702113935513.png)



> :bulb: ์๊ฐ์ฌํ ๊ตฌํํ๊ธฐ



- ์๊ฐ๊ธฐ๋ก์ ํด๋ฆญํ๋ฉด ๊ทธ ์ ๋จ๊ณ๋ก ์ด๋ํ๊ธฐ ์ํด ๋ค์๊ณผ ๊ฐ์ ํจ์๋ฅผ ์ค์ 

  ```react
    jumpTo(step) {
      this.setState({
        stepNumber: step,
        xIsNext: (step % 2) === 0,
      });
    }
  ```

  ![image-20210702114407226](README/image-20210702114407226.png)







---





### 10. ๋ง๋ฌด๋ฆฌ

โ	![image-20210702115205555](README/image-20210702115205555.png)



> โฑ ํ์ต๋ด์ฉ ์ ๋ฆฌ



- Props๋ฅผ ํตํ ์ปดํฌ๋ํธ๊ฐ์ ๋ฐ์ดํฐ ์ ๋ฌ

- ๋ถ๋ชจ-์์ ๊ด๊ณ๋ฅผ ํตํ ์ปดํฌ๋ํธ ์ ์ด

- .slice()์ฐ์ฐ์๋ฅผ ์ฌ์ฉํ square๋ฐฐ์ด ์ฌ๋ณธ ๋ง๋ค๊ธฐ๋ฅผ ํตํด ๋ฐฐ์ด '๋ถ๋ณ์ฑ'

  - https://ko.reactjs.org/tutorial/tutorial.html#why-immutability-is-important

  - ๋ณต์กํ ํน์ง๋ค์ ๋จ์ํ๊ฒ ๋ง๋ฆ
  - ๋ณํ๋ฅผ ๊ฐ์งํจ
  - React์์ ๋ค์ ๋ ๋๋งํ๋ ์๊ธฐ๋ฅผ ๊ฒฐ์ ํจ

- ์๊ฐ์ฌํ ๊ธฐ๋ฅ์ ๋ง๋ค๋ฉด์ ๋ฐฐ์ด '๋์์ ๋ํ ๊ธฐ๋ก ์ ์ฅํ๊ธฐ'

- ๋์ ์ธ ๋ฆฌ์คํธ๋ฅผ ๋ง๋ค๋ ํ ๋นํ๋ 'ํค' ๊ฐ๋

  - https://ko.reactjs.org/tutorial/tutorial.html#picking-a-key



> โฑ ๋๋์ .



Vue๋ฅผ ํ์ฉํ  ๋ ๋ณด๋ค JS์ ๋ํ ์ดํด๊ฐ ๋์ฑ ์ค์ํ๋ค๋ ๊ฒ์ ๋๊ผ์ต๋๋ค.

์ ์ฒด์ ์ธ component ๊ตฌ์กฐ๊ฐ Vue๋ณด๋ค ์ ์ฐํ ๊ตฌ์กฐ๋ฅผ ๊ฐ์ง๊ณ  ์์๊ณ , ๋ฐ์ดํฐ ํ์ฉ ์ธก๋ฉด์์ ๋ ํ์ฉ์ฑ์ด ์ข์ ๊ฒ ๊ฐ์์ต๋๋ค.

์ผ๋จ ๊ฐ๋จํ ํํ ๋ฆฌ์ผ ์ ๋๋ง ํ์ตํ์๋๋ฐ, 

bootstrap์ด๋ Sass์ ๊ฐ์ ํจํค์ง๋ฅผ ํ์ฉํด์ ๋์ฑ ๋ฐ์์ฑ์ด ์ข์ ๊ธฐ๋ฅ๋ค์ ์กฐ๊ธ ๋ ๊ณต๋ถํด ๋ณด๊ณ  ์ถ์์ต๋๋ค.



