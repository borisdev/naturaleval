# oracle-spec

A declarative spec for encoding human norms for system behavior.

The authors of an AI oracle drive what constitutes good AI behavior.

## What is an Oracle?

An AI oracle is a system that provides guidance, decisions, or classifications based on human expertise and values encoded in a structured specification.

## What is an Oracle Spec?

A declarative configuration system for AI behavior governance that allows domain experts to define what constitutes correct AI behavior without needing machine learning expertise.

## Motivation

### Principles

- do not need to code
- can swap different competing AI agent candidates
- can steer the fine-tuning of AI agents
- can get feedback on their directives
- can formulate wholistic evaluations based on a variety of competing concerns
- can formulate evaluation based on many pre and post conditions (states)
- can read and share an AI oracle
- can familiarize themselves with a standard

## Core Innovation

This addresses the fundamental **"alignment specification" problem** - how do domain experts encode their knowledge and values into AI systems without needing to be ML engineers.

## Key Strengths

**1. Separation of Concerns**

```yaml
# Subject matter experts write the "what"
contract.yaml:
  behavior: classify_biohacking_relevance
  criteria: intervention + measurable_outcome

# ML engineers handle the "how"
model_config.py:
  architecture: transformer
  training: fine_tune_on_oracle_spec
```

```yaml
# oracle-spec.yaml
apiVersion: oracle/v1
kind: BehaviorSpec
metadata:
  domain: biohacking_relevance
  version: 2.1.0

spec:
```

## Governance Benefits

**Auditability**: "Why did the AI make this decision?" → "It followed oracle-spec v2.1, section 3.4"
**Accountability**: Clear ownership chain from domain expert → oracle spec → AI behavior
**Transparency**: Stakeholders can read and critique the behavioral specification
**Iteration**: Update specs based on real-world performance without retraining models
