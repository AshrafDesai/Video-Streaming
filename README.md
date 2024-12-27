graph TD
    subgraph Client
        A[Web Browser] --> B[React App]
        B --> C[Video.js Player]
    end

    subgraph Backend Server
        D[Express Server] --> E[Multer]
        E --> F[FFmpeg]
        F --> G[File System]
    end

    subgraph Storage
        G --> H[/uploads/courses/{uuid}/]
        H --> I[index.m3u8]
        H --> J[segment000.ts]
        H --> K[segment001.ts]
    end

    B --1. Upload Video--> D
    C --2. Request HLS Stream--> D
    D --3. Serve HLS Segments--> C

    style A fill:#f9f,stroke:#333
    style D fill:#bbf,stroke:#333
    style F fill:#bfb,stroke:#333
    style H fill:#fbb,stroke:#333