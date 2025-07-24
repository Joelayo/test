# test

graph TD
    subgraph "Azure Cloud"
        subgraph "Data Storage (ADLS Gen2)"
            A[fa:fa-file-code Raw Data] --> B;
            D[🥉 Bronze Layer] --> E[🥈 Silver Layer];
            E --> F[🥇 Gold Layer <br> (Star Schema)];
        end

        subgraph "Processing (Azure Databricks)"
            B[Databricks Job <br> on an Auto-scaling Cluster]
        end

        A --> B;
        B --> D;
    end

    subgraph "Infrastructure as Code"
        I[fa:fa-code Terraform] --> A;
        I --> B;
    end

    subgraph "Analytics"
       F --> H{fa:fa-magnifying-glass-chart Databricks SQL};
       H --> J[fa:fa-user-tie Analysts & BI Tools];
    end
