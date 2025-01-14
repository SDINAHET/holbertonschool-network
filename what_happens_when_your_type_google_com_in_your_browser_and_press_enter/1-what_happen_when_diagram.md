Add a schema to your blog post illustrating the flow of the request created when you type https://www.google.com in your browser and press Enter.

The diagram should show:

    DNS resolution
    that the request hitting server IP on the appropriate port
    that the traffic is encrypted
    that the traffic goes through a firewall
    that the request is distributed via a load balancer
    that the web server answers the request by serving a web page
    that the application server generates the web page
    that the application server request data from the database


```mermaid
graph TD
    A[User Browser] -->|1. DNS Resolution| B[DNS Server]
    B -->|Resolves Domain to IP| C[Server IP (8.8.8.8)]
    C -->|2. TCP/IP Connection on Port 443| D[Firewall]
    D -->|3. Inspects Traffic| E[HTTPS/SSL Encryption]
    E -->|4. Secures Traffic| F[Load Balancer]
    F -->|5. Distributes Request| G[Web Server]

    G -->|6. Serves Static Content| A
    G -->|7. Forwards Dynamic Request| H[Application Server]
    H -->|8. Executes Business Logic| I[Database]
    I -->|9. Retrieves Data| H
    H -->|10. Generates Web Page| G

    %% Detailed Notes for Each Step
    %% User Browser Initiates DNS Resolution
    A:::client -->|Request: www.google.com| B:::dns
    B:::dns -->|Response: IP Address (e.g., 8.8.8.8)| C:::server

    %% TCP/IP Handshake and Port Usage
    C:::server -->|Establishes Connection via Port 443| D:::firewall
    D:::firewall -->|Traffic Inspection| E:::https

    %% Encryption and Secure Transmission
    E:::https -->|Encrypted Traffic| F:::loadbalancer

    %% Load Balancer Distributes Requests
    F:::loadbalancer -->|Routes Traffic to Optimal Server| G:::webserver

    %% Web Server Handles Content
    G:::webserver -->|Static Resources (HTML, CSS, JS)| A:::client
    G:::webserver -->|Dynamic Request Handling| H:::appserver

    %% Application Server Logic Execution
    H:::appserver -->|Queries Database| I:::database
    I:::database -->|Data Response| H:::appserver
    H:::appserver -->|Processes and Generates HTML| G:::webserver

    %% Web Server Responds to Browser
    G:::webserver -->|Delivers Complete Response| A:::client

    %% Classes for Styling
    classDef client fill:#a8e6cf,stroke:#333,stroke-width:2px;
    classDef dns fill:#ff8b94,stroke:#333,stroke-width:2px;
    classDef server fill:#ffcc5c,stroke:#333,stroke-width:2px;
    classDef firewall fill:#dcedc1,stroke:#333,stroke-width:2px;
    classDef https fill:#88d8b0,stroke:#333,stroke-width:2px;
    classDef loadbalancer fill:#ffaaa5,stroke:#333,stroke-width:2px;
    classDef webserver fill:#ffd3b6,stroke:#333,stroke-width:2px;
    classDef appserver fill:#d4a5a5,stroke:#333,stroke-width:2px;
    classDef database fill:#6fc3df,stroke:#333,stroke-width:2px;

    %% Apply Classes to Nodes
    class A client;
    class B dns;
    class C,D,E,F,G,H,I server;
    
```


```plaintext
graph TD
    A[User Browser] -->|1. DNS Resolution| B[DNS Server]
    B -->|Resolves Domain to IP| C[Server IP (8.8.8.8)]
    C -->|2. TCP/IP Connection on Port 443| D[Firewall]
    D -->|3. Inspects Traffic| E[HTTPS/SSL Encryption]
    E -->|4. Secures Traffic| F[Load Balancer]
    F -->|5. Distributes Request| G[Web Server]

    G -->|6. Serves Static Content| A
    G -->|7. Forwards Dynamic Request| H[Application Server]
    H -->|8. Executes Business Logic| I[Database]
    I -->|9. Retrieves Data| H
    H -->|10. Generates Web Page| G

    %% Detailed Notes for Each Step
    %% User Browser Initiates DNS Resolution
    A:::client -->|Request: www.google.com| B:::dns
    B:::dns -->|Response: IP Address (e.g., 8.8.8.8)| C:::server

    %% TCP/IP Handshake and Port Usage
    C:::server -->|Establishes Connection via Port 443| D:::firewall
    D:::firewall -->|Traffic Inspection| E:::https

    %% Encryption and Secure Transmission
    E:::https -->|Encrypted Traffic| F:::loadbalancer

    %% Load Balancer Distributes Requests
    F:::loadbalancer -->|Routes Traffic to Optimal Server| G:::webserver

    %% Web Server Handles Content
    G:::webserver -->|Static Resources (HTML, CSS, JS)| A:::client
    G:::webserver -->|Dynamic Request Handling| H:::appserver

    %% Application Server Logic Execution
    H:::appserver -->|Queries Database| I:::database
    I:::database -->|Data Response| H:::appserver
    H:::appserver -->|Processes and Generates HTML| G:::webserver

    %% Web Server Responds to Browser
    G:::webserver -->|Delivers Complete Response| A:::client

    %% Classes for Styling
    classDef client fill:#a8e6cf,stroke:#333,stroke-width:2px;
    classDef dns fill:#ff8b94,stroke:#333,stroke-width:2px;
    classDef server fill:#ffcc5c,stroke:#333,stroke-width:2px;
    classDef firewall fill:#dcedc1,stroke:#333,stroke-width:2px;
    classDef https fill:#88d8b0,stroke:#333,stroke-width:2px;
    classDef loadbalancer fill:#ffaaa5,stroke:#333,stroke-width:2px;
    classDef webserver fill:#ffd3b6,stroke:#333,stroke-width:2px;
    classDef appserver fill:#d4a5a5,stroke:#333,stroke-width:2px;
    classDef database fill:#6fc3df,stroke:#333,stroke-width:2px;

    %% Apply Classes to Nodes
    class A client;
    class B dns;
    class C,D,E,F,G,H,I server;
```