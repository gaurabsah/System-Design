# HLD Interview Syllabus

An 8-week plan for a software engineer with about 5 years of experience preparing for mid to senior system design interviews. Each week pairs concepts with designs you practice on paper.

- 8 weeks
- 1.5 to 2 hrs per weekday
- 2 to 3 full designs per week from Week 5

## Syllabus

Week 1Foundations

### Estimation, requirements, and APIs

- Request lifecycle: DNS, CDN, load balancer, app servers, database
- Back-of-envelope math: QPS, storage, bandwidth, latency numbers
- Functional vs non-functional requirements; scoping an open-ended problem
- API design: REST vs gRPC, pagination, versioning, idempotency keys

**Checkpoint:** estimate storage and QPS for a URL shortener from scratch in under 5 minutes.

Week 2Data layer

### Databases, replication, and consistency

- SQL vs NoSQL: key-value, document, wide-column, graph; choosing by access pattern
- Indexing, B-trees vs LSM trees, transactions and isolation levels
- Replication (leader-follower, multi-leader, leaderless) and replication lag
- Sharding, hot spots, consistent hashing
- CAP, PACELC, and consistency models (strong, eventual, causal)

**Checkpoint:** justify a database choice for three different workloads and name what you give up in each.

Week 3Caching and async

### Caches, queues, and event streams

- Cache patterns: cache-aside, write-through, write-back; eviction; invalidation
- Failure modes: cache stampede, penetration, avalanche, hot keys
- Message queues vs logs (RabbitMQ vs Kafka); partitions, consumer groups, ordering
- Delivery semantics, idempotent consumers, outbox pattern, dead-letter queues

**Checkpoint:** explain how to prevent duplicate charges across API retries, queue redelivery, and consumer crashes.

Week 4Reliability

### Scaling and failure handling

- Load balancing algorithms, L4 vs L7, service discovery
- Rate limiting algorithms: token bucket, leaky bucket, sliding window
- Timeouts, retries with backoff, circuit breakers, bulkheads, backpressure
- Monolith vs microservices, multi-region design, disaster recovery, observability

**Checkpoint:** walk through what happens, step by step, when a downstream service becomes slow.

Week 5Classic designs I

### Core problems

- URL shortener, including unique ID generation
- Rate limiter (distributed)
- Key-value store
- Notification system
- Web crawler

**Checkpoint:** design each on paper in 40 minutes, then compare against a reference and list what you missed.

Week 6Classic designs II

### Read-heavy and real-time systems

- News feed (fan-out on write vs read)
- Chat application (WebSockets, presence, message ordering)
- Video streaming (upload pipeline, transcoding, CDN)
- File storage and sync (Dropbox)
- Typeahead and search suggestions

**Checkpoint:** for each design, name the main bottleneck and two alternatives you rejected, with reasons.

Week 7Advanced

### Harder problems and deep dives

- Proximity and ride-sharing (geohash, quadtree)
- Payment system (ledger, reconciliation, exactly-once effects)
- Distributed lock and leader election; distributed cache
- Search engine basics: inverted index, ranking, sharded search

**Checkpoint:** go 10 minutes deep on any one component of any design without notes.

Week 8Mocks

### Timed mock interviews and review

- 4 to 6 timed mocks (45 minutes each), with me or with a peer
- Feedback on structure, trade-off clarity, depth, and time management
- Revisit the weakest two topics from earlier weeks

**Checkpoint:** deliver a complete design, including failure handling, inside 45 minutes.

## Interview framework (45 minutes)

1. Clarify requirements, functional and non-functional (5 min)
2. Estimate scale (5 min)
3. Define APIs and the data model (5 to 10 min)
4. Draw the high-level architecture (10 min)
5. Deep-dive on one or two bottlenecks and trade-offs (10 to 15 min)
6. Cover failures, monitoring, and next improvements (5 min)

## Weekly routine

- Weekdays: learn one topic with me, then answer check questions.
- Weekend: attempt a full design alone on paper, then get it critiqued.
- Keep a running list of mistakes and re-test yourself on them every week.

## Resources

- *System Design Interview* Vol 1 and 2, Alex Xu (core text)
- *Designing Data-Intensive Applications*, Martin Kleppmann (depth on Weeks 2 to 4)
- System Design Primer (GitHub), ByteByteGo, Hello Interview (walkthroughs)