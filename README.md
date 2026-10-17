# DevOps Performance Analysis and Scalability Testing

## Project Overview

This project evaluates the performance and scalability of a Kubernetes-hosted web application using Apache JMeter. Load tests were performed with different concurrent user levels to measure response time, throughput, and request failure rates.

## Objectives

- Measure application response time under concurrent load.
- Compare performance at different user levels.
- Analyze throughput and request error rates.
- Identify potential performance bottlenecks.
- Recommend improvements for scalability and reliability.

## Tools and Technologies

- Kubernetes
- Minikube
- Docker Desktop
- Apache JMeter 5.6.3
- Nginx
- Git Bash
- Git and GitHub

## Test Environment

The application was accessed through Kubernetes port forwarding and tested using an HTTP GET request to `127.0.0.1:8080`.

| Parameter | Value |
|---|---|
| Request Method | GET |
| Protocol | HTTP |
| Ramp-up Period | 5 seconds |
| Loop Count | 2 |
| Baseline Users | 5 |
| Increased Users | 10 |

## Performance Test Results

| Metric | 5 Users | 10 Users |
|---|---:|---:|
| Total Samples | 10 | 20 |
| Average Response Time | 23 ms | 3,459 ms |
| Minimum Response Time | 13 ms | 96 ms |
| Maximum Response Time | 292 ms | 8,839 ms |
| Error Rate | 0% | 0% |
| Throughput | 2.3 requests/sec | 2.1 requests/sec |

## Performance Analysis

The baseline test completed ten requests with an average response time of 23 milliseconds. Under the increased load of ten concurrent users, the average response time increased to 3,459 milliseconds, while throughput decreased slightly to 2.1 requests per second. Both tests reported a zero-percent error rate.

These initial results indicate potential performance degradation under increased concurrency. Repeated tests and Kubernetes resource monitoring are required to identify the underlying cause.

## Optimization Recommendations

- Monitor CPU and memory utilization of Kubernetes pods.
- Review Kubernetes resource requests and limits.
- Investigate application and Nginx response latency.
- Evaluate readiness and liveness probes.
- Consider Horizontal Pod Autoscaling when appropriate.
- Repeat tests with gradually increasing user levels.
- Compare average response time, percentile latency, throughput, and error rate.

## Repository Contents

- `DevOps Performance and Scalability Testing.jmx` - JMeter test plan.
- `report/` - Performance analysis report.
- `screenshots/` - Test configuration and results evidence.

## Conclusion

This project demonstrates practical load testing and performance analysis for a Kubernetes-hosted application using Apache JMeter. The results highlight the importance of evaluating response time and throughput under increasing concurrency before making scaling decisions.
