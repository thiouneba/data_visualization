# Data Visualization Framework

![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=for-the-badge&logo=graphql&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![D3.js](https://img.shields.io/badge/D3.js-F9A03C?style=for-the-badge&logo=d3dotjs&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)

> **Academic context:** This project was completed in 2022 as part of the *Non-Traditional Databases* course — MSc in Computer Science, Université de Caen Normandie.

---

## Project Overview

This project involves the design and development of a **full-stack data visualization framework** built on a modern NoSQL architecture. It serves as a practical implementation of the concepts covered in the Non-Traditional Databases module, combining a document-oriented database, a flexible query layer, and an interactive frontend to explore and visualize data dynamically.

The stack was fully containerized using **Docker**, allowing seamless deployment and eliminating environment compatibility issues across machines.

---

## Architecture

```
┌─────────────────────────────────────────┐
│              Browser (Client)           │
│         HTML / CSS / D3.js              │
└────────────────┬────────────────────────┘
                 │ GraphQL queries
┌────────────────▼────────────────────────┐
│           GraphQL API Server            │
│     (schema, resolvers, endpoints)      │
└────────────────┬────────────────────────┘
                 │
┌────────────────▼────────────────────────┐
│              MongoDB                    │
│    (document store / NoSQL backend)     │
└─────────────────────────────────────────┘
         (all services via Docker Compose)
```

---

## Tech Stack

| Technology | Role |
|------------|------|
| MongoDB | NoSQL document database — stores and manages the dataset |
| Mongo Express | Web-based MongoDB admin UI (accessible at `localhost:8081`) |
| GraphQL | Query language and API layer between the database and frontend |
| D3.js | Data-driven visualizations rendered in the browser |
| HTML / CSS | Frontend structure and styling |
| Docker & Docker Compose | Containerization and orchestration of all services |

---

## Key Concepts Applied

- **Non-relational data modeling** — structuring data as flexible JSON documents in MongoDB rather than rigid relational tables
- **GraphQL schema design** — defining types, queries, and resolvers to expose data in a structured, efficient way
- **Data-driven documents** — using D3.js to bind data to DOM elements and generate dynamic, interactive charts
- **Containerized deployment** — packaging every service (API, database, frontend) into isolated Docker containers orchestrated via a single Compose file

---

## Results

The screenshots below show the application's interface and the interactive visualizations produced from the dataset.

<img src="https://github.com/thiouneba/data_visualization/blob/main/Res1.PNG" width="500" />

<img src="https://github.com/thiouneba/data_visualization/blob/main/Res2.PNG" width="500" />

<img src="https://github.com/thiouneba/data_visualization/blob/main/Res3.PNG" width="500" />

---

## Getting Started

### Prerequisites

- [Docker](https://www.docker.com/) and Docker Compose installed on your machine

### Run the project

```bash
# Navigate to the GraphQL service directory
cd graphql

# Remove existing node_modules if present
rm -rf node_modules/

# Build the GraphQL Docker image
docker build -t graphql .

# Return to root and start all services
cd ..
docker-compose -f stack.yml up -d
```

### Access the application

| Service | URL |
|---------|-----|
| Data visualization app | http://localhost:8080 |
| Mongo Express (DB admin) | http://localhost:8081 |

---

## Conclusion

This project provided practical, end-to-end experience with a modern NoSQL-based data stack. Implementing GraphQL as the API layer — rather than a traditional REST API — highlighted the flexibility and precision it offers when querying nested document structures, avoiding the over-fetching and under-fetching problems common in REST architectures.

Containerizing the entire stack with Docker was equally instructive: it reinforced the value of infrastructure-as-code and reproducible environments, ensuring that the application runs identically regardless of the host system. The combination of MongoDB, GraphQL, and D3.js proved well-suited for building interactive, data-rich applications where the shape of the data evolves iteratively.

---

## References

- MongoDB Documentation: https://www.mongodb.com/docs/
- GraphQL Specification: https://spec.graphql.org/
- Bostock, M., Ogievetsky, V., & Heer, J. (2011). D³: Data-Driven Documents. *IEEE Transactions on Visualization and Computer Graphics*, 17(12), 2301–2309.
- Docker Documentation: https://docs.docker.com/
