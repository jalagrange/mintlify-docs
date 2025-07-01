# Dynamic Quiz Generator Documentation

This repository contains the technical documentation for the Dynamic Quiz Generator, an AI-powered assessment tool for personalized learning paths.

## About the Project

The Dynamic Quiz Generator enables learners to assess their knowledge through AI-generated quizzes, helping them identify content gaps and optimize their learning journey.

### Key Features

- **AI-Powered Generation**: Automatically generate quizzes from course content
- **Multiple Question Types**: Support for multiple choice, true/false, fill-in-the-blank, and short answer
- **Instant Feedback**: Get immediate results with topic-based scoring and recommendations  
- **Learning Analytics**: Track progress and identify knowledge gaps over time

## Documentation Development

This documentation is built using [Mintlify](https://mintlify.com), a modern documentation platform.

### Prerequisites

- Node.js 18+
- Mintlify CLI

### Local Development

1. Install the Mintlify CLI globally:
```bash
npm i -g mintlify
```

2. Start the development server:
```bash
mintlify dev
```

3. Open [http://localhost:3000](http://localhost:3000) to view the documentation

### Documentation Structure

- `/technical/` - System architecture and implementation details
- `/api-reference/` - API documentation and integration guides
- `/docs/` - Project planning and development documentation

### Contributing

1. Follow the development workflow outlined in `CLAUDE.md`
2. Check the development backlog in `/docs/development-backlog.md`
3. Create feature planning documents for complex changes in `/docs/feature-planning/`

### Troubleshooting

- If the dev environment isn't running: Run `mintlify install` to re-install dependencies
- Page loads as 404: Make sure you are running in a folder with `docs.json`
- For Mintlify usage guidance: See `/docs/mintlify-usage-guide.md`

## Project Timeline

- **MVP Target**: October 2025
- **Current Phase**: Documentation and architecture development
- **Focus**: Developer documentation first, then user-facing guides

## Support

- **Technical Issues**: [GitHub Issues](https://github.com/go1/dynamic-quiz-creator/issues)
- **General Support**: [support@go1.com](mailto:support@go1.com)