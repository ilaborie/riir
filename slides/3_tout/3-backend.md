+++
title = "Serveur backend"
classes = ["no_title", "spread-steps"]
+++

<style>
article {
    margin-bottom: 2em;
}
</style>

### Backend, Middleware

<!-- pause -->

#### 📦 Crates

- Fondation: [tokio](https://github.com/tokio-rs/tracing), [serde](https://github.com/serde-rs/serde), [tracing](https://github.com/tokio-rs/tracing), [reqwest](https://github.com/seanmonstar/reqwest), [tower](https://github.com/tower-rs/tower), ...
- Serveur: [axum](https://github.com/tokio-rs/axum), [actix-web](https://github.com/actix/actix-web), [tonic](https://github.com/hyperium/tonic), [async-graphql](https://github.com/async-graphql/async-graphql) ...
- Accès DB: [sqlx](https://github.com/launchbadge/sqlx), [diesel](https://github.com/diesel-rs/diesel), [SeaORM](https://github.com/SeaQL/sea-orm), [mongodb](https://github.com/mongodb/mongo-rust-driver) ...
- Cloud: [OpenDAL](https://github.com/apache/opendal), [linkerd2-proxy](https://github.com/linkerd/linkerd2-proxy), [Pinagora](https://github.com/cloudflare/pingora), SDK cloud, ...

<!-- pause -->

### 🪜 Scaffolding

- [🚂 Loco](https://loco.rs/)

<!-- notes -->

parfait pour infrastructure, middleware
Embedded DB: sled, ou sqlite
Messages Queues: Iggy, rdkafka, ..


