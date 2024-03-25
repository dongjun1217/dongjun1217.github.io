# 1.2 서버리스 아키텍처

서버리스 아키텍처는 개발자가 서버 관리와 인프라 관리에 대한 걱정 없이, 애플리케이션과 서비스를 구축할 수 있도록 하는 클라우드 컴퓨팅의 실행 모델입니다. 이 모델에서 클라우드 제공업체가 서버 관리를 자동화하고, 동적으로 리소스를 할당합니다. 서버리스 아키텍처는 특히 이벤트 기반의 애플리케이션과 마이크로서비스에 적합합니다.

---

## 서버리스 컴퓨팅 서비스 비교


서버리스 컴퓨팅은 개발자가 서버 인프라 관리 없이 애플리케이션 기능을 구축 및 배포할 수 있는 클라우드 기반 패러다임입니다. 이는 개발 속도를 높이고 운영 비용을 절감하며 탄력적인 확장성을 제공하는 효과적인 솔루션입니다.


**주요 서비스:**

### AWS Lambda

* **특징:**
    * 풍부한 기능 및 이벤트 소스 지원
    * 광범위한 사용자 기반 및 활발한 커뮤니티
    * 다양한 통합 옵션
    * 뛰어난 성능 및 확장성
    * 다양한 언어 지원 (Python, Node.js, Java, Go, Ruby 등)
    * 1ms 단위로 세분화된  billed duration


* **장점:**
    * 높은 기능 수준
    * 활발한 커뮤니티 및 풍부한 정보
    * 다양한 통합 옵션
    * 뛰어난 성능 및 확장성
    * 세분화된 과금 체계


* **단점:**
    * 상대적으로 느린 실행 속도 (초기 콜드 스타트)
    * 복잡한 디버깅 과정
    * 100MB 제한된 함수 코드 크기


* **활용 사례:**
    * 이미지 리사이징
    * IoT 데이터 처리
    * 스트리밍 데이터 분석
    * 서버리스 웹 애플리케이션 구축
    * 코드 자동 배포
    * 로그 분석


* **주의 사항:**
    * Lambda 함수는 간단하고 재사용 가능하도록 설계해야 합니다.
    * 코드 테스트 및 디버깅에 신경 써야 합니다.
    * Lambda 함수 실행 상태 모니터링 및 보안 관리가 중요합니다.


* **알아두면 유용한 팁:**
    * Lambda Layers를 활용하여 코드 버전 관리 및 공유
    * Lambda@Edge를 사용하여 로컬 네트워크 레이턴시 감소
    * CloudWatch를 사용하여 Lambda 함수 모니터링 및 디버깅
    * AWS SDK를 활용하여 다른 AWS 서비스와 연동

### Azure Functions

* **특징:**
    * 사용 편의성을 강조한 인터페이스
    * 다양한 언어 지원 (C#, JavaScript, Python, F#, Java 등)
    * 포괄적인 Azure 서비스 통합
    * 다양한 템플릿 제공

* **장점:**
    * 직관적인 사용자 인터페이스
    * 다양한 언어 선택 가능
    * Azure 서비스와의 긴밀한 연동
    * 빠른 개발 시작 가능

* **단점:**
    * 기능 범위가 AWS Lambda보다 제한적
    * 비교적 느린 실행 속도
    * HTTP 트리거만 지원

* **활용 사례:**
    * 웹사이트 댓글 알림
    * 데이터 백업
    * 마이크로서비스 구축
    * 모바일 앱 백엔드 개발
    * IoT 데이터 처리
    * 서버리스 웹 API 구축

* **주의 사항:**
    * Azure Functions는 HTTP 트리거 기반으로 작동하며, 복잡한 이벤트 처리에는 적합하지 않을 수 있습니다.
    * Azure 서비스와의 통합에 주목하여 활용하면 효과적입니다.

### Google Cloud Functions

* **특징:**
    * 빠른 실행 속도 (초기 콜드 스타트 최적화)
    * 용이한 디버깅 도구 제공
    * 간편한 코드 배포
    * 다양한 언어 지원 (Node.js, Python, Go, Java 등)
    * HTTP 및 Cloud Pub/Sub 트리거 지원

* **장점:**
    * 뛰어난 성능 및 빠른 실행 속도
    * 효율적인 디버깅 도구
    * 간편한 배포 프로세스
    * 다양한 언어 지원

* **단점:**
    * 기능 범위가 AWS Lambda 및 Azure Functions보다 제한적
    * 상대적으로 부족한 커뮤니티 및 정보
    * Cloud Pub/Sub 트리거 설정이 복잡할 수 있음

* **활용 사례:**
    * 실시간 번역
    * 마이크로서비스 구축
    * 웹사이트 로깅
    * 데이터 스트림 처리
    * 이미지 처리
    * 서버리스 웹 API 구축

* **주의 사항:**
    * Google Cloud Functions는 HTTP 트리거와 Cloud Pub/Sub 트리거만 지원합니다.
    * Cloud Pub/Sub 트리거를 사용할 경우, 메시지 처리 로직 설계에 주의해야 합니다.

* **알아두면 유용한 팁:**
    * Cloud Functions 콘솔 또는 Google Cloud SDK를 사용하여 함수 개발
    * Cloud Debugger를 사용하여 함수 디버깅
    * Cloud Logging을 사용하여 함수 실행 상태 모니터링
    * HTTP 트리거 및 Cloud Pub/Sub 트리거를 상황에 맞게 선택

### 서비스 비교 차트

| 기능 | AWS Lambda | Azure Functions | Google Cloud Functions |
|---|---|---|---|
| 기능 범위 | 풍부함 | 제한적 | 제한적 |
| 실행 속도 | 느림 (초기 콜드 스타트) | 느림 | 빠름 |
| 디버깅 | 복잡 | 쉬움 | 쉬움 |
| 배포 | 간편 | 간편 | 간편 |
| 언어 지원 | 다양함 | 다양함 | 다양함 |
| 트리거 | 다양함 | HTTP | HTTP, Cloud Pub/Sub |
| 통합 | 다양한 AWS 서비스 | 다양한 Azure 서비스 | Google Cloud 서비스 |
| 가격 | 사용량 기반 | 사용량 기반 | 사용량 기반 |

### 결론

서버리스 컴퓨팅 서비스는 다양한 장점을 제공하며, 프로젝트 특성에 따라 적합한 서비스를 선택하는 것이 중요합니다.

* **AWS Lambda:** 풍부한 기능과 활발한 커뮤니티를 원하는 경우
* **Azure Functions:** Azure 서비스와의 긴밀한 연동을 원하는 경우
* **Google Cloud Functions:** 빠른 실행 속도와 간편한 디버깅을 원하는 경우

---

## 이벤트 및 메시지 서비스 비교

이벤트 및 메시지 서비스는 애플리케이션 간의 통신 및 워크플로 자동화를 위한 중요한 도구입니다. 다양한 서비스가 존재하며, 각 서비스마다 고유의 기능과 장단점을 가지고 있습니다.

### Amazon SNS (Simple Notification Service)

* **개요:** 다양한 프로토콜을 통해 이벤트 및 메시지를 전송하는 풀 매니지드 서비스
* **주요 기능:**
  * 다양한 타겟(HTTP, Lambda, SQS 등)에 메시지 전송
  * 유연한 토픽 구독 및 필터링
  * 배송 확장성 및 안정성 보장
* **장점:**
  * 사용 편의성
  * 확장성
  * 안정성
* **단점:**
  * 다른 AWS 서비스와의 긴밀한 통합 필요
  * 유료 서비스

**예시:**

* **새로운 사용자 등록 알림:**
  * 사용자가 웹사이트에 가입하면 SNS 토픽에 메시지를 게시하여 이메일 또는 SMS 알림을 트리거합니다.

```python
import boto3

sns = boto3.client('sns')

topic_arn = 'arn:aws:sns:us-east-1:123456789012:my-topic'

message = '새로운 사용자가 등록했습니다!'

sns.publish(TopicArn=topic_arn, Message=message)
```

* **마이크로서비스 간 통신:**
  * 마이크로서비스 A가 작업을 완료하면 SNS 토픽에 메시지를 게시하여 마이크로서비스 B가 작업을 시작하도록 트리거합니다.

```python
import boto3

sns = boto3.client('sns')

topic_arn = 'arn:aws:sns:us-east-1:123456789012:my-topic'

message = '마이크로서비스 A 작업 완료!'

sns.publish(TopicArn=topic_arn, Message=message)
```

### Amazon SQS (Simple Queue Service)

* **개요:** 메시지 큐잉 서비스
* **주요 기능:**
  * 메시지 큐 생성 및 관리
  * 메시지 전송 및 수신
  * 큐에 대한 여러 작업자 지원
* **장점:**
  * 확장성
  * 안정성
  * 분리된 워크플로 지원
* **단점:**
  * 복잡한 설정
  * 다른 AWS 서비스와의 긴밀한 통합 필요

**예시:**

* **파일 처리 워크플로:**
  * 사용자가 파일을 업로드하면 SQS 큐에 메시지를 추가하여 백엔드 서버가 파일을 처리하도록 트리거합니다.

```python
import boto3

sqs = boto3.client('sqs')

queue_url = 'https://sqs.us-east-1.amazonaws.com/123456789012/my-queue'

message = '새로운 파일 업로드됨!'

sqs.send_message(QueueUrl=queue_url, MessageBody=message)
```

* **데이터 백업 및 복제:**
  * 데이터베이스 변경 사항을 SQS 큐에 넣어 백업 서버로 전송합니다.

```python
import boto3

sqs = boto3.client('sqs')

queue_url = 'https://sqs.us-east-1.amazonaws.com/123456789012/my-queue'

message = '데이터베이스 변경 사항!'

sqs.send_message(QueueUrl=queue_url, MessageBody=message)
```

### Azure Event Grid

* **개요:** 서버리스 컴퓨팅 및 이벤트 기반 워크플로를 위한 이벤트 라우팅 서비스
* **주요 기능:**
  * 다양한 이벤트 소스 및 타겟 지원
  * 이벤트 필터링 및 구독
  * 자동화된 워크플로 생성
* **장점:**
  * 서버리스 아키텍처 지원
  * 다양한 이벤트 소스 및 타겟 지원
  * 자동화된 워크플로 생성
* **단점:**
  * Azure 플랫폼에만 국한
  * 복잡한 설정

**예시:**

* **IoT 알림:**
  * IoT 장치에서 데이터를 보내면 Event Grid를 통해 데이터 분석 서비스로 전송하여 실시간 분석을 수행합니다.

```python
from azure.eventhub import EventHubClient

event_hub_client = EventHubClient('connection_string')

event_data = {'temperature': 25.0, 'humidity': 60.0}

event_hub_client.send_event(event_data)
```

* **서버리스 워크플로:**
  * Event Grid를 통해 Blob Storage에 새 파일이 업로드되면 Azure Functions를 트리거하여 파일 처리를 수행합니다.

```python
def process_blob(blob: Blob, context: Context) -> None:
    """
    Blob 업로드 트리거 함수 예시

    Args:
        blob: Blob 정보
        context: 함수 컨텍스트
    """

    # Blob 내용 처리

    print(f"Blob 이름: {blob.name}")
    print(f"Blob 크기: {blob.size}")
    print(f"Blob 콘텐츠 유형: {blob.content_type}")

```

### Google Cloud Pub/Sub

* **개요:** 풀 매니지드 실시간 메시징 서비스
* **주요 기능:**
  * 메시지 토픽 생성 및 구독
  * 확장 가능한 메시지 전송 및 수신
  * 실시간 스트리밍 지원
* **장점:**
  * 확장성
  * 실시간 스트리밍 지원
  * 다양한 클라이언트 라이브러리 지원
* **단점:**
  * Google Cloud 플랫폼에만 국한
  * 복잡한 설정

**예시:**

* **실시간 채팅:**
  * 사용자가 메시지를 보내면 Pub/Sub 토픽에 게시하여 다른 사용자에게 실시간으로 전달합니다.

```python
from google.cloud import pubsub_v1

publisher = pubsub_v1.PublisherClient()

topic_path = publisher.topic_path('project_id', 'topic_name')

data = b'This is a message.'

publisher.publish(topic_path, data=data)
```

* **로그 스트리밍:**
  * 애플리케이션 로그를 Pub/Sub 토픽에 게시하여 로그 분석 서비스로 전송합니다.

```python
from google.cloud import logging

client = logging.Client()

logger = client.logger('my-logger')

logger.log('This is a log message.')
```

### 선택 가이드

* **사용 편의성:** Amazon SNS
* **확장성:** Amazon SQS, Azure Event Grid, Google Cloud Pub/Sub
* **실시간 스트리밍:** Google Cloud Pub/Sub
* **플랫폼:**
  * AWS: Amazon SNS, Amazon SQS
  * Azure: Azure Event Grid
  * GCP: Google Cloud Pub/Sub

### 결론

각 서비스마다 고유의 장점과 특징을 가지고 있으므로, 프로젝트의 요구 사항에 맞는 서비스를 선택하는 것이 중요합니다.

## 백엔드 서비스 비교

**1. 주요 특징**

| 기능 | Amazon DynamoDB | Google Firestore | Azure Cosmos DB |
|---|---|---|---|
| 데이터 모델 | NoSQL 키-값 저장소 | NoSQL 문서 데이터베이스 | NoSQL 다중 모델 데이터베이스 (키-값, 문서, 그래프) |
| 스케일링 | 자동 | 자동 | 자동 |
| 일관성 | 최종 일관성 | 강력 일관성 (선택 가능) | 강력 일관성 (선택 가능) |
| 쿼리 기능 | 기본적인 쿼리 | 풍부한 쿼리 (Firestore 쿼리 언어) | 풍부한 쿼리 (SQL) |
| 가격 | 사용량 기반 | 사용량 기반 | 사용량 기반 |

**2. 활용 사례**

* **Amazon DynamoDB:**
  * 모바일 및 웹 애플리케이션의 백엔드
  * 게임 데이터 저장
  * IoT 데이터 저장
* **Google Firestore:**
  * 실시간 데이터베이스가 필요한 애플리케이션
  * 오프라인 동기화가 필요한 애플리케이션
  * 모바일 및 웹 애플리케이션의 백엔드
* **Azure Cosmos DB:**
  * 다양한 데이터 모델을 사용하는 애플리케이션
  * 글로벌 규모의 애플리케이션
  * 고성능 및 고가용성이 필요한 애플리케이션

**3. 장단점 비교**

| 서비스 | 장점 | 단점 |
|---|---|---|
| Amazon DynamoDB | 빠른 성능, 뛰어난 확장성, 저렴한 가격 | 기본적인 쿼리 기능, 강력 일관성 지원 안 함 |
| Google Firestore | 실시간 데이터베이스, 오프라인 동기화, 풍부한 쿼리 기능 | 강력 일관성 설정 시 성능 저하 가능성 |
| Azure Cosmos DB | 다양한 데이터 모델 지원, 강력 일관성 지원, 글로벌 규모 지원 | 비교적 높은 가격 |

**4. 선택 가이드**

* **데이터 모델:**
  * 키-값 저장소: DynamoDB
  * 문서 데이터베이스: Firestore, Cosmos DB
  * 그래프 데이터베이스: Cosmos DB
* **일관성:**
  * 최종 일관성: DynamoDB, Firestore (기본 설정)
  * 강력 일관성: Firestore (선택 설정), Cosmos DB
* **쿼리 기능:**
  * 기본적인 쿼리: DynamoDB
  * 풍부한 쿼리: Firestore, Cosmos DB
* **가격:**
  * 저렴: DynamoDB
  * 중간: Firestore
  * 비교적 높음: Cosmos DB
* **기타 고려 사항:**
  * 실시간 데이터베이스 필요 여부
  * 오프라인 동기화 필요 여부
  * 글로벌 규모 지원 필요 여부

**5. 코드 예시**

**Amazon DynamoDB**

```java
import com.amazonaws.services.dynamodbv2.AmazonDynamoDB;
import com.amazonaws.services.dynamodbv2.AmazonDynamoDBClientBuilder;
import com.amazonaws.services.dynamodbv2.document.DynamoDB;
import com.amazonaws.services.dynamodbv2.document.Item;
import com.amazonaws.services.dynamodbv2.document.PutItemOutcome;
import com.amazonaws.services.dynamodbv2.document.Table;

public class DynamoDBExample {

    public static void main(String[] args) {
        AmazonDynamoDB client = AmazonDynamoDBClientBuilder.standard().build();
        DynamoDB dynamoDB = new DynamoDB(client);

        Table table = dynamoDB.getTable("my-table");

        Item item = new Item()
                .withPrimaryKey("id", 123)
                .withString("name", "John Doe");

        PutItemOutcome outcome = table.putItem(item);

        // ...
    }
}
```

**Google Firestore**

```java
import com.google.api.core.ApiFuture;
import com.google.cloud.firestore.Firestore;
import com.google.cloud.firestore.FirestoreOptions;
import com.google.firebase.cloud.FirestoreClient;

public class FirestoreExample {

    public static void main(String[] args) throws Exception {
        FirestoreOptions options = FirestoreOptions.getDefaultInstance();
        Firestore firestore = FirestoreClient.getFirestore(options);

        ApiFuture<com.google.cloud.firestore.DocumentReference> future = firestore.collection("users").document("123").set(
                new com.google.cloud.firestore.DocumentReference("name", "John Doe"));

        // ...
    }
}
```

**Azure Cosmos DB**

```java
import com.azure.cosmos.CosmosClient;
import com.azure.cosmos.CosmosContainer;
import com.azure.cosmos.CosmosDatabase;
import com.azure.cosmos.models.CosmosItem;

public class CosmosDBExample {

    public static void main(String[] args) {
        CosmosClient client = new CosmosClient("connection_string");
        CosmosDatabase database = client.getDatabase("my-database");
        CosmosContainer container = database.getContainer("my-container");

        CosmosItem item = new CosmosItem()
                .setId("123")
                .setProperty("name", "John Doe");

        container.createItem(item);

        // ...
    }
}
```

## API 게이트웨이 및 관리 비교

**1. 주요 기능**

| 기능 | Amazon API Gateway | Azure API Management | Google Cloud Endpoints |
|---|---|---|---|
| API 게이트웨이 | 제공 | 제공 | 제공 |
| API 관리 | 기본 | 고급 | 고급 |
| 보안 | 기본 | 고급 | 고급 |
| 모니터링 | 기본 | 고급 | 고급 |
| 가격 | 사용량 기반 | 사용량 기반 | 사용량 기반 |

**2. 활용 사례**

* **API 게이트웨이:**
  * 다양한 백엔드 서비스에 대한 프록시 역할
  * API 트래픽 관리
  * API 보안
* **API 관리:**
  * API 버전 관리
  * API 문서 생성 및 관리
  * API 분석

**3. 장단점 비교**

| 서비스 | 장점 | 단점 |
|---|---|---|
| Amazon API Gateway | 사용 편의성, 저렴한 가격 | 기본적인 기능 제공 |
| Azure API Management | 고급 API 관리 기능, 다양한 정책 설정 | 비교적 높은 가격 |
| Google Cloud Endpoints | 고급 API 관리 기능, Google Cloud Platform과의 긴밀한 통합 | 비교적 높은 가격 |

**4. 선택 가이드**

* **API 관리 기능 필요 여부:**
  * 기본적인 기능만 필요: Amazon API Gateway
  * 고급 API 관리 기능 필요: Azure API Management, Google Cloud Endpoints
* **사용 플랫폼:**
  * AWS: Amazon API Gateway
  * Azure: Azure API Management
  * GCP: Google Cloud Endpoints
* **가격:**
  * 저렴: Amazon API Gateway
  * 고급 기능 필요 시: Azure API Management, Google Cloud Endpoints

## 애플리케이션 통합 서비스
- AWS Step Functions
- Azure Logic Apps
- Google Cloud Workflows

## 서버리스 애플리케이션 모니터링 및 디버깅
- AWS CloudWatch
- Azure Monitor
- Google Cloud Operations Suite

서버리스 아키텍처는 개발자가 애플리케이션 로직에 더 집중할 수 있게 해주며, 인프라 관리의 복잡성을 줄여줍니다. 또한, 사용한 만큼만 비용을 지불하는 비용 효율적인 모델을 제공하여, 빠르게 확장하는 애플리케이션에 이상적입니다. 이러한 아키텍처는 마이크로서비스, IoT 애플리케이션, 백엔드 API 개발 등 다양한 분야에서 활용될 수 있습니다.

source: `{{ page.path }}`
