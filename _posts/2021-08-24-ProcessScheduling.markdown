---
layout: post
title:  "Process Scheduling"
date:   2021-08-24 11:23:36 +0530
categories: OperatingSystem
---

### **Process Scheduling** <br/>

**Why we need process scheduling?** <br/>
	<br/>
	- Maximize CPU use and quickly switch processes onto CPU core <br/>
	- Process scheduler selects among available processes for next execution on CPU core <br/>
	- Maintains scheduling queues of processes: <br/>
		+ Ready Queue - set all processes residing in main memory, ready and waiting to execute <br/>
		+ Wait Queue - set of processes waiting for an event (I/O) <br/>





<!-- 
프로세스란? <br/>
	- 실행중에 있는 프로그램을 얘기한다. <br/>

프로세스의 구조 <br/>
	-**텍스트 섹션**: 프로그램을 실행시키는 실행파일 내의 명령어 <br/>
	-**프로그램 카운터**: 프로세서의 레지스터 <br/>
	-**스택**: 지역변수, 함수 호출시 전달되는 파라미터를 위한 메모리 영역 <br/>
	-**데이터 섹션**: 전역변수나, static 변수의 할당 <br/>
	-**힙**: 동적할당을 위한 메모리 영역 <br/>

프로그램은 디스크의 저장된 수동적인 객체, 프로세스는 활동적인 객체를 의미 <br/>
	- 해당 프로그램의 실행파일이 메모리로 로드가 되면 프로그램은 프로세스가 된다<br/>
	- 하나의 프로그램이 여러개의 프로세스가 될 수 있음<br/>

-->



<!-- ---
Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse

```javascript
const Razorpay = require('razorpay');

let rzp = Razorpay({
	key_id: 'KEY_ID',
	secret: 'name'
});

// capture request
rzp.capture(payment_id, cost)
	.then(function (data) {
		return 2;
	})
```

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/ -->
