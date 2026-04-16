# ACE (Autonomous Career Engine)

An AI automation system to auto-apply for jobs on your behalf.

## Overview

ACE (Autonomous Career Engine) is an AI-powered automation system designed to streamline the job application process. The system functions as a multi-agent orchestration tool that:

- Fetches job posts from LinkedIn, Indeed, and other job platforms
- Stores job posts in a PostgreSQL database with priority scoring
- Applies predefined filters to find the right jobs based on title, years of experience, locations, etc.
- Automatically generates applications by finding application forms and answering questions
- Creates customized motivation letters and cover letters
- Implements a human-in-the-loop review process for applications
- Generates interview preparation materials and simulations

## Features

### Job Discovery & Filtering
- Automated job scraping from multiple platforms
- Intelligent filtering based on user preferences
- Priority scoring algorithm for job opportunities

### Application Automation
- Automatic form filling for job applications
- AI-generated responses to application questions
- Personalized cover letters and motivation letters
- Human review process with approve/edit/reject options

### Interview Preparation
- Customized interview questions based on job requirements
- Company research and background information
- Interactive interview simulation with feedback
- Follow-up question support during practice sessions

## Architecture

The system is built with a multi-agent orchestration approach:

- **Job Discovery Agent**: Scours job platforms and populates the database
- **Filtering Agent**: Applies user-defined criteria to rank opportunities
- **Application Agent**: Crafts personalized applications for each position
- **Review Agent**: Assists in the human-in-the-loop approval process
- **Interview Prep Agent**: Generates materials and conducts simulations
- **Feedback Agent**: Provides analysis and improvement suggestions

## Setup

1. Clone the repository
2. Install dependencies with UV: `uv sync`
3. Configure environment variables in `.env`
4. Set up PostgreSQL database
5. Run the application: `uv run main.py`

## Contributing

Contributions are welcome! Please read our contributing guidelines for details on how to submit pull requests, report issues, and suggest improvements.

## License

This project is licensed under the MIT License - see the LICENSE file for details.