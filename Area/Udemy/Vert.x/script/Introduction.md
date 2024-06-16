

Hello and welcome to the Learn Vertex Reactive Microservices Course Instruction.

We are living in a world where the internet is used by more than 3 billion people.

A lot of them use it on a daily basis, and this trend will likely increase until every human on earth will use it.

```
on a daily basis : 매일
likely : 가능성
```

Another trend is that more and more organizations are using cloud services.

If you are working as software engineer in a company, it is very likely that you deploy your application to a cloud environment like Amazon Web Service, Google Cloud Platform or Microsoft Azure.

Regarding to Gartner, more than 75% indicate that they have a cloud first strategy.

```
위 표현은 잘못된 표현임. 아래처럼 바꿔야 함.
According to Gartner, more than 75% indicate that they have a cloud first strategy.

Indicate : 나타내다, 보여주다, 지시하다
예문:
- The survey results indicate a high level of customer satisfaction.
  - 설문 조사 결과는 높은 수준의 고객 만족도를 나타냅니다.
- Please indicate your choice on the form.
  - 양식에 당신의 선택을 표시해 주세요.
- The signs indicate the direction to the nearest hospital.
  - 표지판은 가장 가까운 병원의 방향을 지시합니다.

Strategy : 전략
예문:
- Our company needs a new marketing strategy to attract more customers.
  - 우리 회사는 더 많은 고객을 유치하기 위해 새로운 마케팅 전략이 필요합니다.
- The general devised a strategy to win the battle.
  - 장군은 전투에서 이기기 위한 전략을 세웠습니다.
- Chess is a game of strategy and skill.
  - 체스는 전략과 기술의 게임입니다.

```

```
Gartner는 정보 기술 (IT) 연구 및 자문 회사입니다. 주로 IT 관련 시장 분석, 리서치, 자문 서      비스, IT 트렌드 예측 등을 제공하여 기업들이 전략적 결정을 내리는 데 도움을 줍니다. Gartner      는 특히 다음과 같은 서비스를 제공합니다:

1. **리서치 보고서**: 다양한 IT 주제에 대한 심층적인 분석과 보고서를 제공합니다.
2. **마켓 리더십 분석**: 매년 발행하는 Magic Quadrant 보고서를 통해 특정 기술 분야의 주요 기업들을 분석하고 평가합니다.
3. **컨퍼런스 및 이벤트**: IT 전문가들을 위한 글로벌 컨퍼런스와 이벤트를 개최하여 최신 트렌드와 기술을 공유합니다.
4. **자문 서비스**: 기업들이 IT 전략을 수립하고 구현하는 데 필요한 조언과 지침을 제공합니다.

Gartner의 분석과 보고서는 IT 업계에서 널리 인정받고 있으며, 많은 기업들이 전략적 결정을 내리는 데 있어 중요한 참고 자료로 사용합니다.
```
 

Deploying an application is just one step.

The other is that the application needs to handle the user demand and users have certain expectations of a modern application.

	    demand
	        1. 수요: 소비자가 특정 상품이나 서비스를 구매하길 원하는 양입니다. 가격, 소득 수준, 개인 취향 등 여러 요인에 의해 영향을 받습니다.
	            예: "There is a high demand for electric vehicles due to environmental concerns." (환경 문제로 인해 전기 자동차에 대한 수요가 높다.)
	        2. 요구: 어떤 것을 강하게 요청하거나 필요로 하는 상태입니다. 개인이나 집단이 특정 행동, 제품, 권리 등을 요구하는 경우를 말합니다.
	            예: "The workers demand better working conditions." (근로자들은 더 나은 근무 조건을 요구한다.)
	        3. 법률 용어로의 사용: 법률에서는 특정 행동을 하도록 요구하는 공식적인 요청이나 명령을 의미하기도 합니다.
	        예: "The demand letter was sent to the company for unpaid wages." (미지급 임금에 대해 회사에 요구서가 보내졌다.)

	    certain : 특정한, 확실한
	    expectation
		    기대, 예상, 기대치와 같은 의미를 가집니다. 보통 무엇인가를 향한 사람들의 예측, 바람, 또는 요구 사항과 관련된 상황에서 사용됩니다. 개인적인 기대일 수도 있고, 직장, 학교, 또는 다른 환경에서의 성과에 대한 기대일 수도 있습니다. 예를 들어, "The teacher's expectations for her students are very high"라는 문장에서는 선생님이 그녀의 학생들에 대해 가지고 있는 높은 기대를 의미합니다.


We want our web services to respond fast and have low latencies.

	latencies : 주로 시간의 지연을 나타내는 단어입니다. 특히, 컴퓨터 과학 분야에서는 데이터 전송, 응답 시간 등과 같은 프로세스의 시간 지연을 설명할 때 사용됩니다. 따라서 "latencies"는 데이터가 전송되거나 처리되는 동안 발생하는 지연이나 지연의 여러 형태를 의미합니다.

The applications should be highly available 24 over seven 365 days a year.
	The applications should be highly available 24/7, 365 days a year.

The application needs to be scalable and ideally autoscale on higher user demands.
	ideally
		이상적으로, 이상적인 상황에서, 이상적으로는의 의미를 가지고 있습니다. 예를 들어, "Ideally, we should finish this project by the end of the week"는 "이상적으로는, 우리는 이번 주말까지 이 프로젝트를 끝내야 합니다"라는 의미입니다.

And last but not least, the applications need to be failure resistant.

Even if there is a failure in the application, not the whole system should go down.

It should stay up and return a response in a timely manner.

Now you might ask why I'm telling you this.

Because this demand requires reactive back end applications.

For this reason, Eclipse Vertex was built.

Vertex is a toolkit to build reactive applications on the Java virtual machine.

It was one of the first pure reactive frameworks.

It is mature, used at many companies and found its way into the cloud native framework.

Quarkus.

But first, let's look at the term reactive.

What does it mean and why do we need it?

The term reactive originated from the Reactive manifesto.

The latest version of this manifesto was published in the year 2014, and since that time more and more frameworks and applications are adapting to it.

The terms message driven, elastic, resilient and responsive are very important characteristics of a reactive system.

So let's break them down.

First we have the term message driven, which is the core characteristic of a reactive application to enable all the others.

A reactive application reacts to certain events by combining it with asynchronous programming and asynchronous message handling.

The application is able to avoid undefined states of overload and scale out to have more event handlers.

In Vertex.

This is done by the vertex event loops.

Vertex also has an actor like deployment model, and the actors are called Vertex.

These verticals can communicate over the vertex event bus via messages and by using promise and future.

It allows asynchronous programming.

In the Vertex Cross section, we will learn how to use these functionalities.

Next.

We have elastic and resilient.

Elastic means that we can scale up the number of JVM threads or processes to handle more load.

Resilient means that we can react to failure and not crash the application, but instead be able to recover from it and service all requests for the users of our application.

These two characteristics are enabled by the message driven approach.

Last but not least, we have responsive.

Everyone knows this.

Opening up an app on the phone and waiting for 10s to see the content is no fun.

You will likely stop using this app.

The reactive manifesto states to react fast to responses, return them quickly on success or failure on high load.

The responsiveness should be guaranteed by scaling up more instances and making sure to meet the user's demand.

Now we know what the reactive application is, but when do we need it?

Can a monolithic application be reactive or only microservices?

I would say both.

And monolithic application avoids inter-service communications, but it very likely exposes an API which is available to other systems.

Or directly to the user interface.

Additionally, most of the applications are interacting with a data store using a data access layer.

Every time the application is interacting with other systems, applying the reactive principles makes sense.

In Vertex this can be achieved.

The Http server is reactive and also the data access.

If we have a microservice architecture, using a reactive approach is even more important.

Imagine one service is not available.

Then the calling microservice should still respond fast and handle this error case properly.

After the service recovered, the full functionality is restored and all the users will be happy using your application.

With this knowledge.

Let's move on to the next lecture and check out the course content.