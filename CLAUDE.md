# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

ACE (Autonomous Career Engine) is an AI automation system designed to auto-apply for jobs on behalf of the user. The system functions as a multi-agent orchestration tool that:

1. Fetches job posts from LinkedIn, Indeed, and other job platforms
2. Stores job posts in a PostgreSQL database with priority scoring
3. Applies predefined filters to identify suitable positions
4. Automatically creates and submits job applications
5. Generates interview preparation materials and simulations

## Core Features

### Job Discovery & Filtering
- Scrapes job postings from multiple platforms (LinkedIn, Indeed, etc.)
- Applies filters based on job title, years of experience (YOE), locations, and other criteria
- Assigns priority scores to job opportunities

### Application Generation
- Identifies application forms for each job posting
- Auto-generates responses to application questions
- Creates customized motivation letters and cover letters
- Implements human-in-the-loop review process with four options:
  - Approve application as-is
  - Approve with edits
  - Reject application
  - Request revisions

### Interview Preparation
- Generates interview preparation materials for approved applications
- Creates relevant questions and suggested readings
- Provides company overviews and background information
- Offers interview simulation with feedback
- Supports iterative question-and-answer sessions with follow-up capabilities

## Project Structure

This is a Python-based backend project with the following directory structure:

```
.
├── backend/
│   ├── app/
│   │   ├── agents/
│   │   ├── api/
│   │   ├── models/
│   │   ├── schemas/
│   │   └── services/
│   └── tests/
├── frontend/
└── .env
```

## Backend Architecture

The backend follows a multi-agent orchestration architecture:

- `app/agents/` - Autonomous agents for job discovery, application creation, and interview prep
- `app/api/` - API endpoints for job data, applications, and interview simulations
- `app/models/` - Database models for jobs, applications, and interview data
- `app/schemas/` - Pydantic schemas for data validation across all components
- `app/services/` - Orchestration layer coordinating agent interactions and business logic
- `tests/` - Unit and integration tests for all components

## Multi-Agent Orchestration

The system employs several specialized AI agents:

1. **Job Discovery Agent** - Scours job platforms and populates the database
2. **Filtering Agent** - Applies user-defined criteria to rank opportunities
3. **Application Agent** - Crafts personalized applications for each position
4. **Review Agent** - Assists in the human-in-the-loop approval process
5. **Interview Prep Agent** - Generates materials and conducts simulations
6. **Feedback Agent** - Provides analysis and improvement suggestions

## Data Flow

1. Job Discovery → Database Storage → Filtering/Ranking
2. Ranked Jobs → Application Generation → Human Review
3. Approved Applications → Submission + Interview Prep Creation
4. Interview Prep → Simulation Sessions → Feedback Loop

## Development Environment

- Python project with standard directory structure
- PostgreSQL database for job and application storage
- Environment variables managed through `.env` file
- GitHub PAT configured for potential GitHub integrations

## Common Development Tasks

1. Implementing scraping agents for job platform integration
2. Developing filtering algorithms and priority scoring mechanisms
3. Creating application generation and customization workflows
4. Building the human-in-the-loop review interface
5. Designing interview preparation and simulation features
6. Implementing feedback analysis and improvement suggestions
7. Writing tests for agent behaviors and data processing workflows

## Testing

Tests should be organized to mirror the application structure:
- Unit tests for individual agents and their logic
- Integration tests for API endpoints and database interactions
- Functional tests for end-to-end job application workflows
- Performance tests for scraping and processing pipelines
- User acceptance tests for the human-in-the-loop review process