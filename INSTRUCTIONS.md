# Instructions

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

## Getting Started

### Prerequisites
- Docker and Docker Compose (for running ELK stack examples)
- Node.js (for Node.js example)
- Basic understanding of Docker and containerization
- Familiarity with log management concepts

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

## Troubleshooting

### Docker Issues
- Ensure Docker is running: `docker ps`
- Check Docker logs: `docker-compose logs`
- Restart containers: `docker-compose restart`

### Port Conflicts
If ports are already in use, modify the `docker-compose.yml` file to use different ports.

### Memory Issues
Elasticsearch requires at least 2GB of RAM. Adjust Docker memory settings if needed.

## Additional Resources

- [Elasticsearch Documentation](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html)
- [Logstash Documentation](https://www.elastic.co/guide/en/logstash/current/index.html)
- [Kibana Documentation](https://www.elastic.co/guide/en/kibana/current/index.html)

## Author

* **Or Assayag** - *Initial work* - [orassayag](https://github.com/orassayag)
* Or Assayag <orassayag@gmail.com>
* GitHub: https://github.com/orassayag
* StackOverflow: https://stackoverflow.com/users/4442606/or-assayag?tab=profile
* LinkedIn: https://linkedin.com/in/orassayag
