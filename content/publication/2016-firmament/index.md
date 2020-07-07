---
abstract: Centralized datacenter schedulers can make high-quality placement decisions
  when scheduling tasks in a cluster.  Today, however, high-quality placements come
  at the cost of high latency at scale, which degrades response time for interactive
  tasks and reduces cluster utilization.<br/><br/>This paper describes Firmament,
  a centralized scheduler that scales to over ten thousand machines at subsecond placement
  latency even though it continuously reschedules all tasks via a min-cost max-flow
  (MCMF) optimization. Firmament achieves low latency by using multiple MCMF algorithms,
  by solving the problem incrementally, and via problem-specific optimizations.<br/><br/>
  Experiments with a Google workload trace from a 12,500-machine cluster show that
  Firmament improves placement latency by 20× over Quincy, a prior centralized scheduler
  using the same MCMF optimization.  Moreover, even though Firmament is centralized,
  it matches the placement latency of distributed schedulers for workloads of short
  tasks. Finally, Firmament exceeds the placement quality of four widely-used centralized
  and distributed schedulers on a real-world cluster, and hence improves batch task
  response time by 6×.
abstract_short: " "
authors: [Ionel Gog, Malte Schwarzkopf, AdamGleave, Robert Watson, Steven Hand]
date: "2016-11-02"
image_preview: ""
publication: Proceedings of the 12th USENIX Symposium on Operating Systems Design and Implementation
publication_short: OSDI
publication_types: ["1"]
title: "Firmament: Fast, Centralized Cluster Scheduling at Scale"
url_code: https://github.com/camsas/firmament
url_pdf: https://www.usenix.org/system/files/conference/osdi16/osdi16-gog.pdf
url_project: http://firmament.io/
---

