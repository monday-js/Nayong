[[node.js] About](<https://nodejs.org/en/about/>) 을 보고 작성한 게시글 입니다.

</br>

## About Node.js

- Javascript로 서버 프로그래밍을 할 수 있도록 도와주는 플랫폼.
- 비동기적인 Javascript 런타임 환경에 따라, 확장성있는 네트워크 어플리케이션을 위하여 제작되었다.
- 많은 연결들이(connections) 동시에 다뤄질 수 있다. 
- callback이 죽었으나, 만약 아무 일도 끝나지 않았다면 node는 잠들 것!
- 그 어떤 함수도 I/O를 직접적으로 수행하지 않는다. 그래서, 프로세스는 NEVER BLOCK.
- lock하지 않기 때문에, dead-locking에 상당히 강하다.
- HTTP는 node.js의 **일급 객체**
  - 일급 객체의 조건
    - 변수나 데이타에 할당 할 수 있어야 한다.
    - 객체의 인자로 넘길 수 있어야 한다.
    - 객체의 리턴값으로 리턴 할수 있어야 한다.
- 스트리밍을 위해, 그리고 지연되는 것을 막기 위한 언어.
- 스레드 없이 디자인 되어져 있다. 근데 이건 다양한 core 기능을 이용할 수 있다는 것은 아니다. 자식 프로세스는 fork되어질 수 있다. 
- core의 로드밸런싱을 위한 과정에서, 소켓을 공유할 수 있다. 

</br>

#### 예제

```javascript
const http = require('http');

const hostname = '127.0.0.1';
const port = 3000;

const server = http.createServer((req, res) => {
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

server.listen(port, hostname, () => {
  console.log(`Server running at http://${hostname}:${port}/`);
});
```

