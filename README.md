# End-to-End Quality Intelligence Framework (QE 1.0)

A production-grade Quality Engineering framework that transforms automation execution into **release-level quality intelligence** using CI/CD pipelines, critical test analysis, and centralized Allure dashboards.

---

## Overview

The **End-to-End Quality Intelligence Framework** is a QE 1.0–level system designed to extend traditional automation into a **decision-driven quality platform**.

Unlike conventional frameworks that focus only on pass/fail execution, this framework provides **actionable insights** required for release readiness and risk assessment, aligned with real-world practices used in modern product organizations.

---

## Key Objective

The primary goal of this framework is to answer one critical question:

**“Is this build safe to release?”**

It achieves this by combining automated testing with quality metrics, test criticality, and CI/CD-driven visibility.

---

## Live Quality Dashboard

**Allure Dashboard (GitHub Pages)**
[https://debasish-87.github.io/End-to-End-Quality-Intelligence-Framework/](https://debasish-87.github.io/End-to-End-Quality-Intelligence-Framework/)

The dashboard is automatically generated and published after every pipeline execution, providing centralized visibility for QA, engineering, and stakeholders.

---

## What Makes This a Quality Intelligence Framework

Traditional automation answers:

> Did the tests pass?

This framework answers:

> What is the release risk?

Core intelligence capabilities include:

* Smoke vs Regression confidence separation
* Critical test impact awareness
* Severity-driven risk visibility
* CI/CD-integrated release readiness reporting

---

## Core Capabilities

### Test Automation Coverage

| Layer               | Technology         |
| ------------------- | ------------------ |
| UI Automation       | Selenium WebDriver |
| API Automation      | RestAssured        |
| Database Validation | MySQL              |
| Test Runner         | TestNG             |
| Language            | Java 17            |

---

### Suite-Based Execution Strategy

| Suite      | Purpose                           | Typical Usage     |
| ---------- | --------------------------------- | ----------------- |
| Smoke      | Fast validation of critical paths | Pull requests     |
| Regression | Full functional coverage          | Nightly / release |
| Critical   | Business-blocking scenarios       | Release gating    |

Suite control is managed through:

* `smoke.xml`
* `regression.xml`
* TestNG groups (`Smoke`, `Regression`, `Critical`)

---

### Quality Metrics Engine

The framework computes and exposes:

* Total tests executed
* Pass and fail percentages
* Critical test failures
* Suite-level execution confidence
* Historical trend readiness via Allure

These metrics enable **data-driven quality discussions** instead of subjective assessments.

---

### Release Decision Engine

The decision engine consolidates execution data into release-oriented outcomes such as:

```
SMOKE SUITE     : PASS
REGRESSION     : 95%
CRITICAL FAILS : 1

FINAL DECISION : HOLD RELEASE
```

This mirrors the release review process followed in real engineering organizations.

---

## Architecture Overview

```
Code Commit
   ↓
CI/CD Pipeline (GitHub Actions)
   ↓
Build and Test Execution
   ↓
Quality Intelligence Layer
   ├── UI Automation
   ├── API Automation
   ├── Database Validation
   ├── Smoke / Regression Suites
   ├── Critical Test Analysis
   ↓
Quality Metrics Engine
   ↓
Allure Centralized Dashboard
   ↓
Release Decision Visibility
```

---

## Project Structure

```
End-to-End-Quality-Intelligence-Framework
│
├── pom.xml
├── testng.xml
├── smoke.xml
├── regression.xml
├── README.md
│
├── src
│   ├── main
│   │   ├── java
│   │   │   ├── base
│   │   │   ├── pages
│   │   │   ├── api
│   │   │   ├── intelligence
│   │   │   │   ├── metrics
│   │   │   │   └── decision
│   │   │   └── utils
│   │   └── resources
│   │       ├── config.properties
│   │       ├── environment.properties
│   │       └── log4j2.xml
│   │
│   └── test
│       ├── java
│       │   ├── tests
│       │   │   ├── ui
│       │   │   └── api
│       │   └── intelligence
│       │       ├── QualityMetricsTest.java
│       │       └── ReleaseDecisionTest.java
│       └── resources
│           ├── testdata
│           └── categories.json
│
├── allure-results
├── logs
└── .github/workflows
    └── allure-deploy.yml
```

---

## Test Execution

Run all tests:

```bash
mvn clean test
```

Run smoke suite:

```bash
mvn clean test "-DsuiteXmlFile=smoke.xml"
```

Run regression suite:

```bash
mvn clean test "-DsuiteXmlFile=regression.xml"
```

Headless execution for CI:

```bash
mvn clean test -Dheadless=true
```

---

## Reporting

Local report:

```bash
mvn allure:serve
```

CI/CD reporting:

* Reports generated after test execution
* Automatically deployed to GitHub Pages
* Centralized and versioned visibility

---

## CI/CD Integration

The GitHub Actions pipeline:

* Executes tests on every push
* Generates Allure reports
* Publishes reports to GitHub Pages

Workflow configuration:

```
.github/workflows/allure-deploy.yml
```

---

## How to Explain This Project in an Interview

“I designed a Quality Intelligence Framework that integrates UI, API, and database automation with CI/CD pipelines. It goes beyond execution by analyzing critical test failures and producing release-level quality visibility through centralized dashboards.”

This demonstrates **Quality Engineering ownership**, not just automation skills.

---

## Intended Audience

This framework reflects quality practices used in:

* Product-based engineering teams
* SaaS organizations
* CI/CD-driven delivery models

It is designed for engineers focused on:

* Release confidence
* Risk-based testing
* Scalable automation
* Stakeholder visibility

---

## Author

Debasish
Quality Engineering | SDET | CI/CD Automation

Email: [debasishm8765@gmail.com](mailto:debasishm8765@gmail.com)
GitHub: [https://github.com/Debasish-87](https://github.com/Debasish-87)

---
