# Fraud Detection in Transaction Graph (Neo4j)

This project aims to develop and implement algorithms and techniques to detect fraudulent activities within transactional data. By analyzing various attributes and patterns within transaction records and relationships between customers and terminals, the project seeks to identify suspicious behavior that may indicate fraudulent transactions. Key components of the project include simulating data, conceptual modelling of the data (UML), logical design of the graph (Neo4j), creating various transaction graphs, querying the database using Cypher, and reporting the execution times of the queries.

> [!IMPORTANT]
> If you wish to store the graphs locally on the machine (Neo4j Desktop) instead of cloud versions (Aura), please make sure that you download and run the project locally on the machine as well, and do NOT use platforms such as Google Colab. The reason is that the local database runs by default on the bold URI `bolt://localhost:7687`, which is NOT accessible remotely.

> [!TIP]
> Click on the button below to preview the project report.
> 
> [![Read the Paper](https://img.shields.io/badge/Report-PDF-red)](https://github.com/tabaraei/transaction-graph-neo4j/blob/master/latex/Fraud_Detection_Transaction_Graph.pdf)

## Neo4j Installation
The objective of this project is to first create 3 different databases of sizes 50Mb, 100Mb, and 200Mb, respectively. The following steps are taken sequentially to achieve this:
- Download and install the [Neo4j Desktop](https://neo4j.com/download/).
- In the first step, we have to create a database in the Neo4j Desktop application, let's name it `TransactionGraph`. We set `user = "neo4j", password="12345678"` as the required authentications.
- We run the TransactionGraph on the default bold URI `bolt://localhost:7687`.
- We attempt to create three different databases, namely `TG50`, `TG100`, and `TG200`, respectively. The naming convention denotes the desired size of data to be stored in each of the databases. An additional `TGtest` database would be also created for test purposes.
- In addition, since the `CALL apoc.periodic.iterate` operation improves performance by parallelization and batching, to benefit the fast responses as the datasets scale, we have to install `APOC` simply as described below:
  - Open Neo4j Desktop
  - Select `Manage` on the database of interest
  - Open the `Plugins` tab
  - Click Install in the `APOC` box and wait until you see a green check mark near "APOC"

## Python Installation
- This project was developed and tested on `Python` (version `3.9.13`).
- Clone the project using `git clone https://github.com/tabaraei/transaction-graph-neo4j.git`, or directly download the zip file, and store the `transaction-graph-neo4j` codebase on desired directory in your local machine.
- Once the installation is performed, navigate to the codebase as `cd transaction-graph-neo4j`.
- Run the commands below sequentially to install the requirements in Windows OS. Keep in mind that the commands below will attempt to create a virtual Python environment in the project directory (in a subfolder named `venv`), and will install all the packages inside `requirements.txt` file accordingly:
  ```shell
  py -3 -m venv venv
  venv/Scripts/activate
  pip install --upgrade pip
  pip install -r requirements.txt
  ```
- Finally, open the codebase in the browser by running `jupyter notebook`, where you can view, edit, and run the `transaction_graph_neo4j.ipynb`.

## Sections
The project structure is divided into the following sections:
| Section                        | Description                                                                       |
|--------------------------------|-----------------------------------------------------------------------------------|
| Transaction Data Simulator     | Python scripts for simulating transactions data of different size                 |
| Conceptual Model               | Design of the UML class diagrams of the entities and relationships                |
| Logical Model                  | Design choices regarding the graph data structure                                 |
| Transaction Graph Generation   | Creating scaled simulated datasets and inserting into graph database using Cypher |
| Experiments                    | Various queries in Cypher to detect fraudulent transactions                       |
