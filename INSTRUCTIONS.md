# Setup and Usage Instructions

## Table of Contents

1. [About This Repository](#about-this-repository)
2. [What's Included](#whats-included)
3. [Prerequisites](#prerequisites)
4. [System Requirements](#system-requirements)
5. [Initial Setup](#initial-setup)
6. [Install Dependencies](#install-dependencies)
7. [Getting Started](#getting-started)
8. [Learning Path](#learning-path)
9. [Common Tasks](#common-tasks)
10. [Available Commands](#available-commands)
11. [Development Commands](#development-commands)
12. [Running Scripts](#running-scripts)
13. [Troubleshooting](#troubleshooting)
14. [Best Practices](#best-practices)
15. [Extending the Application](#extending-the-application)
16. [Additional Resources](#additional-resources)
17. [External Resources](#external-resources)
18. [Support](#support)
19. [Author](#author)

## About This Repository

This repository is a collection of learning resources and examples for the ELK Stack (Elasticsearch, Logstash, Kibana). It was created in April 2019 as a reference for future learning and experimentation with the ELK Stack.

## What's Included

### 1. Docker ELK Example (`docker-elk-master.zip`)

A Docker Compose setup for running the complete ELK stack locally.

**Contents:**

- Elasticsearch configuration
- Logstash pipeline configuration
- Kibana dashboard setup
- Docker Compose orchestration

**To use:**

```bash
unzip docker-elk-master.zip
cd docker-elk-master
docker-compose up
```

### 2. Node.js ELK Example (`node-elk-master.zip`)

A Node.js application demonstrating logging integration with the ELK stack.

**Contents:**

- Node.js application with Winston logger
- Logstash configuration for Node.js logs
- Docker Compose setup for ELK stack
- Sample application code

**To use:**

```bash
unzip node-elk-master.zip
cd node-elk-master
npm install
docker-compose up
node app.js
```

### 3. Learning Resources (`misc/documents/links.txt`)

Curated links to tutorials and resources:

- Udemy course on Elasticsearch 6 and Elastic Stack
- Docker ELK GitHub repository
- Node ELK GitHub repository

## Prerequisites

### System Requirements

- \*\*Docker and Docker Compose (for running ELK stack examples)
- **Node.js** (for Node.js example, v12 or higher)
- **Operating System**: macOS, Linux, or Windows with WSL
- **Memory**: At least 4GB of RAM available for Docker
- **Disk Space**: Sufficient space for Docker images and volumes

### Knowledge Prerequisites

- Basic understanding of Docker and containerization
- Familiarity with log management concepts

## Initial Setup

### 1. Clone the Repository

```bash
git clone https://github.com/orassayag/elasticsearch-logstash-kibana-learning.git
cd elasticsearch-logstash-kibana-learning
```

### 2. Extract Examples

Choose and extract one of the example archives:

```bash
# For Docker ELK Stack example
unzip docker-elk-master.zip

# For Node.js with ELK example
unzip node-elk-master.zip
```

## Install Dependencies

### For Docker ELK Stack

No additional dependencies needed beyond Docker and Docker Compose.

### For Node.js Example

```bash
cd node-elk-master
npm install
```

## Getting Started

### Basic Setup

1. Clone this repository:

   ```bash
   git clone https://github.com/orassayag/elasticsearch-logstash-kibana-learning.git
   cd elasticsearch-logstash-kibana-learning
   ```

2. Extract one of the example projects:

   ```bash
   unzip docker-elk-master.zip
   # or
   unzip node-elk-master.zip
   ```

3. Follow the specific instructions in each extracted project's README

## Learning Path

### Beginners

1. Start with the Udemy course link in `misc/documents/links.txt`
2. Extract and run `docker-elk-master.zip` to get hands-on experience
3. Experiment with Kibana dashboards at `http://localhost:5601`

### Intermediate

1. Explore the `node-elk-master.zip` example
2. Modify Logstash pipelines to parse different log formats
3. Create custom Kibana visualizations
4. Experiment with Elasticsearch queries

### Advanced

1. Configure custom index patterns in Elasticsearch
2. Build complex Logstash filters
3. Create advanced Kibana dashboards
4. Integrate ELK with your own applications

## Common Tasks

### Accessing Services

After running `docker-compose up`:

- **Elasticsearch**: http://localhost:9200
- **Logstash**: Configured to receive logs on port 5000
- **Kibana**: http://localhost:5601

### Testing Elasticsearch

```bash
curl http://localhost:9200
```

### Viewing Logs in Kibana

1. Open http://localhost:5601
2. Go to Management > Index Patterns
3. Create an index pattern (e.g., `logstash-*`)
4. Navigate to Discover to view logs

## Available Commands

### Docker ELK Stack Commands

```bash
# Start the ELK stack
cd docker-elk-master
docker-compose up

# Start in detached mode
docker-compose up -d

# Stop the ELK stack
docker-compose down

# View logs
docker-compose logs

# View logs for a specific service
docker-compose logs elasticsearch
docker-compose logs logstash
docker-compose logs kibana
```

### Node.js Example Commands

```bash
# Install dependencies
cd node-elk-master
npm install

# Start the application
node app.js

# Start with npm (if configured)
npm start
```

## Development Commands

### Docker ELK Stack Development

```bash
# Rebuild containers (if you make changes to configurations)
docker-compose up --build

# Clean up volumes (warning: deletes all data)
docker-compose down -v
```

### Node.js Example Development

```bash
# Restart the application
# (Stop with Ctrl+C and run again)
node app.js
```

## Running Scripts

### Docker ELK Stack

1. Navigate to the extracted directory:

```bash
cd docker-elk-master
```

2. Start the stack:

```bash
docker-compose up
```

### Node.js Example

1. Navigate to the extracted directory:

```bash
cd node-elk-master
```

2. Install dependencies:

```bash
npm install
```

3. Start the stack:

```bash
docker-compose up -d
```

4. Start the application:

```bash
node app.js
```

## Troubleshooting

### Docker Issues

- Ensure Docker is running: `docker ps`
- Check Docker logs: `docker-compose logs`
- Restart containers: `docker-compose restart`

### Port Conflicts

If ports are already in use, modify the `docker-compose.yml` file to use different ports.

### Memory Issues

Elasticsearch requires at least 2GB of RAM. Adjust Docker memory settings if needed.

## Best Practices

### Logging Best Practices

1. **Structured Logging**: Use JSON format for logs
2. **Log Levels**: Use appropriate log levels (debug, info, warn, error)
3. **Context**: Include relevant context in logs (timestamps, request IDs)
4. **Sensitive Data**: Avoid logging sensitive information
5. **Log Rotation**: Implement log rotation to manage disk space

### ELK Stack Best Practices

1. **Resource Allocation**: Allocate sufficient memory to Elasticsearch
2. **Index Management**: Use index templates and ILM (Index Lifecycle Management)
3. **Performance**: Optimize Logstash filters for performance
4. **Security**: Secure Elasticsearch and Kibana with authentication
5. **Monitoring**: Monitor the ELK stack itself

### Development Best Practices

1. **Local Testing**: Test configurations locally before production
2. **Version Control**: Keep all configurations in version control
3. **Documentation**: Document all custom configurations and pipelines
4. **Backup**: Regularly backup Elasticsearch data
5. **Testing**: Test log processing pipelines with sample data

## Extending the Application

### Adding Custom Logstash Pipelines

1. Navigate to the extracted `docker-elk-master/logstash/` directory
2. Add or modify pipeline configuration files
3. Restart Logstash:

```bash
docker-compose restart logstash
```

### Creating Custom Kibana Dashboards

1. Access Kibana at http://localhost:5601
2. Create visualizations and dashboards
3. Export dashboards for reuse

### Integrating with Other Applications

1. Configure your application to send logs to Logstash on port 5000
2. Update Logstash configurations to parse your log format
3. Create Kibana dashboards for your application logs

## Additional Resources

- [Elasticsearch Documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
- [Logstash Documentation](https://www.elastic.co/guide/en/logstash/current/index.html)
- [Kibana Documentation](https://www.elastic.co/guide/en/kibana/current/index.html)

## External Resources

- [Official Elastic Documentation](https://www.elastic.co/guide/)
- [Docker Documentation](https://docs.docker.com/)
- [Node.js Documentation](https://nodejs.org/docs/)
- [Winston Logger Documentation](https://github.com/winstonjs/winston)

## Support

For questions, issues, or contributions:

- **GitHub Issues**: [https://github.com/orassayag/elasticsearch-logstash-kibana-learning/issues](https://github.com/orassayag/elasticsearch-logstash-kibana-learning/issues)
- **Email**: orassayag@gmail.com

## Author

- **Or Assayag** - _Initial work_ - [orassayag](https://github.com/orassayag)
- Or Assayag <orassayag@gmail.com>
- GitHub: https://github.com/orassayag
- StackOverflow: https://stackoverflow.com/users/4442606/or-assayag?tab=profile
- LinkedIn: https://linkedin.com/in/orassayag

---

**Last Updated**: June 2026
**Version**: 1.0.0
