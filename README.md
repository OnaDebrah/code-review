# AI-Driven Code Review Tool

[![Scala Version](https://img.shields.io/badge/scala-2.13%2B-blue.svg)](https://www.scala-lang.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

An intelligent code review system that combines static analysis with machine learning to automatically detect bugs and suggest improvements in Scala code.

## Key Features

- **Pattern Learning**: Analyzes codebases to identify common patterns and anti-patterns
- **Adaptive Rules**: Generates review rules automatically based on code patterns
- **Confidence Scoring**: Provides suggestions with confidence levels
- **Feedback Integration**: Learns from developer feedback to improve suggestions
- **Anomaly Detection**: Flags unusual code structures that deviate from norms

## Architecture Overview

### Core Components

```scala
sealed trait SeverityLevel
case object High extends SeverityLevel
case object Medium extends SeverityLevel
case object Low extends SeverityLevel

case class Suggestion(
  lineNumber: Int,
  message: String,
  fix: String,
  severity: SeverityLevel = Medium,
  ruleId: String = "",
  confidence: Double = 1.0,
  suggestionId: String = UUID.randomUUID().toString
)
