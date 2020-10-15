---
title: Structured Performance Tests
layout: post
tags: ["performance tests","models","structured programming","NUnit"]
---
 
Performance tests are hard, but performance tests are also just tests. Concepts and techniques from more familiar types of automated testing then also apply to performance tests, if we apply them with care. I spoke at this idea at the [World Conference on Next Generation Testing 2020](https://www.unicomlearning.com/2020/WCNGT_2020/) this week.

As part of this talk, I pull out some correspondences between classic unit test constructs in NUnit, and equivalents when doing performance testing. This doesn't mean performance tests are unit tests - there are important differences when dealing at a system level and when the test fixtures include hardware. It does let us reuse some common toolsets and repeat our performance testing in a systematic way.

Agile techniques, and DevOps techniques and tools, are a big enabler for this. For example, when hardware is a test fixture, being able to redeploy according to a repeatable playbook is the equivalent of a test setup. This is much cheaper and easier when the application team already maintain an automated deployment script as part of routine development and deployment.

[Slides here](/slides/structured_performance_tests_20201015.pdf).

