# Resources for Microservices Platform

## 📺 Video Tutorials
- [Microservices Architecture with Kubernetes & Istio (2026)](https://www.youtube.com/watch?v=CZ3wIuvmHeM) - freeCodeCamp complete course
- [Building Microservices with Node.js & NestJS](https://www.youtube.com/watch?v=XUSHH0E-7zk) - Traversy Media (updated)
- [Kubernetes Tutorial 2026](https://www.youtube.com/watch?v=X48VuDVv0do) - TechWorld with Nana - **ESSENTIAL**
- [Microservices with Spring Boot & Spring Cloud](https://www.youtube.com/watch?v=BnknNTN8icw) - Java Brains

## 📚 Written Tutorials
- [Microservices Architecture Guide](https://microservices.io/) - Complete pattern library - **ESSENTIAL**
- [Building Microservices (2nd Edition)](https://www.oreilly.com/library/view/building-microservices/9781491950340/) - Sam Newman - **MUST READ**
- [Kubernetes Documentation](https://kubernetes.io/docs/home/) - Official K8s docs
- [12-Factor App Methodology](https://12factor.net/) - Best practices for microservices

## 🔧 Tools & Libraries

### API Gateway
- [Kong](https://konghq.com/) - Cloud-native API gateway - **RECOMMENDED**
- [NGINX](https://www.nginx.com/) - High-performance web server/reverse proxy
- [Traefik](https://traefik.io/) - Modern HTTP reverse proxy
- [Express Gateway](https://www.express-gateway.io/) - Node.js API gateway

### Service Discovery
- [Consul](https://www.consul.io/) - Service mesh and discovery - **RECOMMENDED**
- [Eureka](https://github.com/Netflix/eureka) - Netflix service registry
- [etcd](https://etcd.io/) - Distributed key-value store
- [Zookeeper](https://zookeeper.apache.org/) - Coordination service

### Message Brokers
- [RabbitMQ](https://www.rabbitmq.com/) - Message broker (AMQP) - **RECOMMENDED**
- [Apache Kafka](https://kafka.apache.org/) - Event streaming platform
- [NATS](https://nats.io/) - High-performance messaging
- [Redis Streams](https://redis.io/topics/streams-intro) - Lightweight alternative

### Container Orchestration
- [Kubernetes](https://kubernetes.io/) - Container orchestration - **INDUSTRY STANDARD**
- [Docker Swarm](https://docs.docker.com/engine/swarm/) - Simpler alternative
- [Nomad](https://www.nomadproject.io/) - HashiCorp orchestrator
- [Amazon ECS](https://aws.amazon.com/ecs/) - AWS container service

### Service Mesh
- [Istio](https://istio.io/) - Complete service mesh - **RECOMMENDED**
- [Linkerd](https://linkerd.io/) - Lightweight service mesh
- [Consul Connect](https://www.consul.io/docs/connect) - HashiCorp service mesh
- [AWS App Mesh](https://aws.amazon.com/app-mesh/) - AWS service mesh

### Observability
- [Jaeger](https://www.jaegertracing.io/) - Distributed tracing - **RECOMMENDED**
- [Zipkin](https://zipkin.io/) - Alternative tracing
- [OpenTelemetry](https://opentelemetry.io/) - Observability framework
- [Prometheus](https://prometheus.io/) - Metrics and monitoring
- [Grafana](https://grafana.com/) - Visualization dashboards

### Logging
- [ELK Stack](https://www.elastic.co/elk-stack) - Elasticsearch, Logstash, Kibana
- [Loki](https://grafana.com/oss/loki/) - Log aggregation by Grafana - **RECOMMENDED**
- [Fluentd](https://www.fluentd.org/) - Data collector
- [Graylog](https://www.graylog.org/) - Log management

## 💻 GitHub Repositories
- [Microservices Demo](https://github.com/GoogleCloudPlatform/microservices-demo) - Google Cloud example - **STUDY THIS**
- [Awesome Microservices](https://github.com/mfornos/awesome-microservices) - Curated resources
- [Spring Petclinic Microservices](https://github.com/spring-petclinic/spring-petclinic-microservices) - Java example
- [Go Microservices](https://github.com/harlow/go-micro-services) - Go implementation
- [Node.js Microservices](https://github.com/goldbergyoni/nodebestpractices#6-microservices) - Best practices

## 📖 Learning Resources

### Microservices Patterns
- [Microservices.io Patterns](https://microservices.io/patterns/index.html) - Complete pattern library - **ESSENTIAL**
- [Circuit Breaker Pattern](https://martinfowler.com/bliki/CircuitBreaker.html) - Martin Fowler
- [Saga Pattern](https://microservices.io/patterns/data/saga.html) - Distributed transactions
- [API Gateway Pattern](https://microservices.io/patterns/apigateway.html) - Gateway design

### Kubernetes
- [Kubernetes Basics](https://kubernetes.io/docs/tutorials/kubernetes-basics/) - Official tutorial
- [Kubernetes the Hard Way](https://github.com/kelseyhightower/kubernetes-the-hard-way) - Deep understanding
- [Kubernetes Patterns](https://k8spatterns.io/) - Design patterns for K8s
- [Production Kubernetes](https://www.oreilly.com/library/view/production-kubernetes/9781492092292/) - O'Reilly book

### DevOps & CI/CD
- [GitOps](https://www.gitops.tech/) - GitOps methodology
- [ArgoCD Documentation](https://argo-cd.readthedocs.io/) - GitOps for K8s
- [Jenkins Best Practices](https://www.jenkins.io/doc/book/pipeline/pipeline-best-practices/) - CI/CD patterns

### Distributed Systems
- [Designing Data-Intensive Applications](https://dataintensive.net/) - Martin Kleppmann - **MUST READ**
- [Building Microservices](https://samnewman.io/books/building_microservices/) - Sam Newman
- [Release It!](https://pragprog.com/titles/mnee2/release-it-second-edition/) - Production patterns

## 🌐 Cloud Platforms & Services
- [AWS ECS/EKS](https://aws.amazon.com/containers/) - AWS container services
- [Google Kubernetes Engine](https://cloud.google.com/kubernetes-engine) - GCP managed K8s
- [Azure Kubernetes Service](https://azure.microsoft.com/en-us/services/kubernetes-service/) - Azure K8s
- [DigitalOcean Kubernetes](https://www.digitalocean.com/products/kubernetes) - Affordable K8s

## 📚 Architecture Diagrams & Examples

### Typical Microservices Architecture
```
┌─────────────────────────────────────────────────────────┐
│ API Gateway │
│ (Kong / NGINX / Traefik) │
└─────────────────┬───────────────────────────────────────┘
│
┌─────────────┼─────────────┬─────────────┐
│ │ │ │
┌───▼────┐ ┌───▼────┐ ┌───▼────┐ ┌───▼────┐
│ Auth │ │Product │ │ Order │ │Payment │
│Service │ │Service │ │Service │ │Service │
└───┬────┘ └───┬────┘ └───┬────┘ └───┬────┘
│ │ │ │
┌───▼────┐ ┌──▼─────┐ ┌──▼─────┐ ┌──▼─────┐
│Postgres│ │MongoDB │ │Postgres│ │ Redis │
└────────┘ └────────┘ └────────┘ └────────┘


     Message Broker (RabbitMQ / Kafka)
┌──────────────────────────────────────┐
│  Events: OrderCreated, PaymentProcessed, etc. │
└──────────────────────────────────────┘
Service Discovery (Consul / Eureka / etcd)
Distributed Tracing (Jaeger / Zipkin)
Centralized Logging (ELK / Loki)
Monitoring (Prometheus + Grafana)
```


## 🚀 Docker Compose Example
```yaml
# docker-compose.yml
version: '3.8'

services:
  api-gateway:
    image: kong:latest
    ports:
      - "8000:8000"
      - "8001:8001"
    environment:
      KONG_DATABASE: postgres
      KONG_PG_HOST: postgres
    depends_on:
      - postgres

  auth-service:
    build: ./services/auth
    ports:
      - "3001:3000"
    environment:
      DATABASE_URL: postgresql://user:pass@postgres:5432/auth
      RABBITMQ_URL: amqp://rabbitmq:5672
    depends_on:
      - postgres
      - rabbitmq

  product-service:
    build: ./services/product
    ports:
      - "3002:3000"
    environment:
      MONGO_URL: mongodb://mongo:27017/products
      RABBITMQ_URL: amqp://rabbitmq:5672
    depends_on:
      - mongo
      - rabbitmq

  order-service:
    build: ./services/order
    ports:
      - "3003:3000"
    environment:
      DATABASE_URL: postgresql://user:pass@postgres:5432/orders
      RABBITMQ_URL: amqp://rabbitmq:5672
    depends_on:
      - postgres
      - rabbitmq

  rabbitmq:
    image: rabbitmq:3-management
    ports:
      - "5672:5672"
      - "15672:15672"

  postgres:
    image: postgres:15
    environment:
      POSTGRES_USER: user
      POSTGRES_PASSWORD: pass
    volumes:
      - postgres-data:/var/lib/postgresql/data

  mongo:
    image: mongo:6
    volumes:
      - mongo-data:/data/db

  jaeger:
    image: jaegertracing/all-in-one:latest
    ports:
      - "16686:16686"
      - "6831:6831/udp"

  prometheus:
    image: prom/prometheus
    volumes:
      - ./prometheus.yml:/etc/prometheus/prometheus.yml
    ports:
      - "9090:9090"

  grafana:
    image: grafana/grafana
    ports:
      - "3000:3000"
    depends_on:
      - prometheus

volumes:
  postgres-data:
  mongo-data:
🔧 Service Communication Example (gRPC)
protobuf

// order.proto
syntax = "proto3";

package order;

service OrderService {
  rpc CreateOrder(CreateOrderRequest) returns (Order);
  rpc GetOrder(GetOrderRequest) returns (Order);
  rpc ListOrders(ListOrdersRequest) returns (OrderList);
}

message CreateOrderRequest {
  string user_id = 1;
  repeated OrderItem items = 2;
  string payment_method = 3;
}

message Order {
  string id = 1;
  string user_id = 2;
  repeated OrderItem items = 3;
  double total = 4;
  string status = 5;
  int64 created_at = 6;
}

message OrderItem {
  string product_id = 1;
  int32 quantity = 2;
  double price = 3;
}
TypeScript

// order-service.ts (Node.js implementation)
import * as grpc from '@grpc/grpc-js';
import * as protoLoader from '@grpc/proto-loader';

const packageDefinition = protoLoader.loadSync('order.proto');
const orderProto = grpc.loadPackageDefinition(packageDefinition).order;

const server = new grpc.Server();

server.addService(orderProto.OrderService.service, {
  createOrder: async (call, callback) => {
    const { user_id, items, payment_method } = call.request;
    
    // Business logic
    const order = await createOrder(user_id, items, payment_method);
    
    // Publish event to message broker
    await publishEvent('OrderCreated', order);
    
    callback(null, order);
  },
  
  getOrder: async (call, callback) => {
    const order = await getOrderById(call.request.id);
    callback(null, order);
  },
});

server.bindAsync(
  '0.0.0.0:50051',
  grpc.ServerCredentials.createInsecure(),
  () => {
    console.log('Order service running on port 50051');
    server.start();
  }
);
```

### 📊 Event-Driven Communication (RabbitMQ)
```TypeScript

// event-publisher.ts
import amqp from 'amqplib';

export class EventPublisher {
  private connection: amqp.Connection;
  private channel: amqp.Channel;

  async connect() {
    this.connection = await amqp.connect(process.env.RABBITMQ_URL);
    this.channel = await this.connection.createChannel();
    await this.channel.assertExchange('events', 'topic', { durable: true });
  }

  async publish(eventType: string, data: any) {
    const message = JSON.stringify({
      type: eventType,
      data,
      timestamp: new Date().toISOString(),
    });

    this.channel.publish('events', eventType, Buffer.from(message), {
      persistent: true,
    });

    console.log(`Published event: ${eventType}`);
  }
}

// event-subscriber.ts
export class EventSubscriber {
  async subscribe(eventType: string, handler: (data: any) => Promise<void>) {
    const connection = await amqp.connect(process.env.RABBITMQ_URL);
    const channel = await connection.createChannel();

    await channel.assertExchange('events', 'topic', { durable: true });
    const { queue } = await channel.assertQueue('', { exclusive: true });
    await channel.bindQueue(queue, 'events', eventType);

    channel.consume(queue, async (msg) => {
      if (msg) {
        const event = JSON.parse(msg.content.toString());
        await handler(event.data);
        channel.ack(msg);
      }
    });
  }
}

// Usage in payment-service
const subscriber = new EventSubscriber();
subscriber.subscribe('OrderCreated', async (order) => {
  console.log('Processing payment for order:', order.id);
  await processPayment(order);
});
```

### 🛡️ Circuit Breaker Pattern
```TypeScript

// circuit-breaker.ts
enum CircuitState {
  CLOSED = 'CLOSED',
  OPEN = 'OPEN',
  HALF_OPEN = 'HALF_OPEN',
}

export class CircuitBreaker {
  private state = CircuitState.CLOSED;
  private failureCount = 0;
  private successCount = 0;
  private nextAttempt = Date.now();

  constructor(
    private threshold = 5,
    private timeout = 60000,
    private monitoringPeriod = 10000
  ) {}

  async execute<T>(fn: () => Promise<T>): Promise<T> {
    if (this.state === CircuitState.OPEN) {
      if (Date.now() < this.nextAttempt) {
        throw new Error('Circuit breaker is OPEN');
      }
      this.state = CircuitState.HALF_OPEN;
    }

    try {
      const result = await fn();
      this.onSuccess();
      return result;
    } catch (error) {
      this.onFailure();
      throw error;
    }
  }

  private onSuccess() {
    this.failureCount = 0;

    if (this.state === CircuitState.HALF_OPEN) {
      this.successCount++;
      if (this.successCount >= this.threshold) {
        this.state = CircuitState.CLOSED;
        this.successCount = 0;
      }
    }
  }

  private onFailure() {
    this.failureCount++;
    
    if (this.failureCount >= this.threshold) {
      this.state = CircuitState.OPEN;
      this.nextAttempt = Date.now() + this.timeout;
      console.log(`Circuit breaker opened. Will retry at ${new Date(this.nextAttempt)}`);
    }
  }
}

// Usage
const breaker = new CircuitBreaker();

async function callExternalService() {
  return breaker.execute(async () => {
    const response = await fetch('https://external-api.com/data');
    return response.json();
  });
}
```

### 📈 Distributed Tracing (OpenTelemetry)
```TypeScript

import { NodeTracerProvider } from '@opentelemetry/sdk-trace-node';
import { JaegerExporter } from '@opentelemetry/exporter-jaeger';
import { Resource } from '@opentelemetry/resources';
import { SemanticResourceAttributes } from '@opentelemetry/semantic-conventions';

const provider = new NodeTracerProvider({
  resource: new Resource({
    [SemanticResourceAttributes.SERVICE_NAME]: 'order-service',
  }),
});

const exporter = new JaegerExporter({
  endpoint: 'http://jaeger:14268/api/traces',
});

provider.addSpanProcessor(new BatchSpanProcessor(exporter));
provider.register();

// Usage in your service
import { trace } from '@opentelemetry/api';

const tracer = trace.getTracer('order-service');

async function createOrder(userId: string, items: any[]) {
  const span = tracer.startSpan('createOrder');
  
  try {
    span.setAttribute('user.id', userId);
    span.setAttribute('items.count', items.length);
    
    // Your business logic
    const order = await saveOrderToDatabase(items);
    
    span.setStatus({ code: SpanStatusCode.OK });
    return order;
  } catch (error) {
    span.setStatus({
      code: SpanStatusCode.ERROR,
      message: error.message,
    });
    throw error;
  } finally {
    span.end();
  }
}
```

### ☸️ Kubernetes Deployment Example
```YAML

# order-service-deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: order-service
  labels:
    app: order-service
spec:
  replicas: 3
  selector:
    matchLabels:
      app: order-service
  template:
    metadata:
      labels:
        app: order-service
    spec:
      containers:
      - name: order-service
        image: your-registry/order-service:latest
        ports:
        - containerPort: 3000
        env:
        - name: DATABASE_URL
          valueFrom:
            secretKeyRef:
              name: db-secrets
              key: postgres-url
        - name: RABBITMQ_URL
          valueFrom:
            configMapKeyRef:
              name: app-config
              key: rabbitmq-url
        resources:
          requests:
            memory: "256Mi"
            cpu: "250m"
          limits:
            memory: "512Mi"
            cpu: "500m"
        livenessProbe:
          httpGet:
            path: /health
            port: 3000
          initialDelaySeconds: 30
          periodSeconds: 10
        readinessProbe:
          httpGet:
            path: /ready
            port: 3000
          initialDelaySeconds: 5
          periodSeconds: 5

apiVersion: v1
kind: Service
metadata:
  name: order-service
spec:
  selector:
    app: order-service
  ports:
  - protocol: TCP
    port: 80
    targetPort: 3000
  type: ClusterIP

apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: order-service-hpa
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: order-service
  minReplicas: 2
  maxReplicas: 10
  metrics:
  - type: Resource
    resource:
      name: cpu
      target:
        type: Utilization
        averageUtilization: 70


```

