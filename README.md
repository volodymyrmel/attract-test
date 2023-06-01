# attract-test
In this test using simle Docker Alpine image. in yml file, I used stable version ngnx version (not latest ) if used latest, there is the problem with service starting after updating version. 
The same behaviour with php image.

Theoretical Part
https://app.cloudcraft.co/view/1089401a-cecb-40bf-bdb8-20db10c87d1f?key=819b7d22-73f5-4b7a-9620-42736f2a7935

                       ┌─────────────────┐
                       │     Internet    │
                       └─────────────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │   AWS Load      │
                       │   Balancer      │
                       └─────────────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │    Amazon EC2   │
                       │   Instances    │
                       └─────────────────┘
                                │
                                ▼
                       ┌─────────────────┐
                       │   Amazon RDS    │
                       │   Database     │
                       └─────────────────┘
                                │
                                ▼
                      ┌──────────────────┐
          ┌─────────▶│    Application   │◀──────────┐
          │           │   Load Balancer │           │
          │           └──────────────────┘           │
          │                      │                    │
          │                      ▼                    │
          │           ┌──────────────────┐           │
          └───────────│   Amazon S3     │───────────┘
                      │   (Static       │
                      │   Content)      │
                      └──────────────────┘
----

                       ┌─────────────────┐                   ┌─────────────────┐
                       │   Internet      │                   │   Internet      │
                       └─────────────────┘                   └─────────────────┘
                                │                                     │
                                ▼                                     ▼
                       ┌─────────────────┐                   ┌─────────────────┐
                       │   Load         │                   │   Load         │
                       │   Balancer     │                   │   Balancer     │
                       └─────────────────┘                   └─────────────────┘
                                │                                     │
                                ▼                                     ▼
                       ┌─────────────────┐                   ┌─────────────────┐
                       │   Frontend     │                   │   Backend      │
                       │   Servers      │                   │   Servers      │
                       └─────────────────┘                   └─────────────────┘
                                │                                     │
                                ▼                                     ▼
                       ┌─────────────────┐                   ┌─────────────────┐
                       │   Amazon S3    │                   │   Database     │
                       │   (Static      │                   │   (e.g., Amazon │
                       │   Content)     │                   │   RDS)         │
                       └─────────────────┘                   └─────────────────┘
