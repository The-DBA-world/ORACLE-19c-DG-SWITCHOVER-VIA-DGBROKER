# ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/f5af6603-8bcb-46bf-9058-d248415cfa89)

The Oracle DataGuard broker is an integrated unit that manage and monitor Primary and Standby databases together. The Broker configuration can be accessed via Oracle Enterprise Manager Cloud Control or the Oracle Data Guard command-line interface (DGMGRL).
A switchover is a role reversal between the primary database and its standby databases. A switchover operation guarantees no data loss. This is typically done for planned maintenance of the primary system. During a switchover, the primary database transitions to a standby role and the standby database transitions to the primary role. The transition occurs without having to recreate either database. DataGuard configuration setups can be referred at my post DG SETUP.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/4e03defd-609a-4ae1-a207-7e959435c3bd)

ENVIRONMENT

ENVIRONMENT | SOURCE PRIMARY| TARGER STANBY | 
--- | --- | --- | 
OS Version | Oracle Linux Server 7.9 | Oracle Linux Server 7.9
HOSTNAME | OMmac1.localdomain | SOMmac1.localdomain
IP ADDRESS | 192.168.56.230 | 192.168.56.240
DB NAME | uzma19c | uzma19c
DB UNIQUE NAME | uzma19c | suzma19c
DB VERSION | 19.3.0 | 19.3.0

ON PRIMARY: ENABLE BROKER

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/331bdfb4-332b-400a-970c-daa66d9f3179)

ON PRIMARY: CHECK DGBROKER CONFIGURATION FILES.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/04257fa0-118c-400f-948e-d3e89d448c5a)

ON STANDBY: ENABLE BROKER

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/09332ab4-9cde-4864-b874-ccbc1eaf50c9)

ON STANDBY: CHECK DGBROKER CONFIGURATION FILES.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/e893027e-7e26-4a10-a76e-199d16ce9e4b)

ON PRIMARY: TNSPING PRIMARY DB

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/cee94d99-8723-4562-a03e-9160e2e19ddf)

ON PRIMARY: TNSPING STANDBY DB

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/5385c6aa-4f12-4a06-b2ea-568e09b691d8)

ON STANDBY: TNSPING PRIMARY DB

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/e1c8d1e9-688c-4d65-a7b8-a4a6628b791d)

ON STANDBY: TNSPING STANDBY DB

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/7eba29ad-62fa-4f35-b5a0-f84cbd3a9416)

ON PRIMARY: REGISTER THE PRIMARY DB WITH DGBROKER.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/3695449a-00d2-48fe-b75e-a11eed322e63)

ON PRIMARY: NOW ADD STANDBY DB WITH DGBROKER.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/56442a80-4b67-47fe-80ce-b18cbf2145b4)

ON PRIMARY: NOW ENABLE DGBROKER.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/0e441d25-027d-485e-808c-247eeef95ec7)

ON PRIMARY DGBROKER: SHOW DGBROKER CONFIGURATION.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/e029f719-a580-4ec1-b317-af657a3e762d)

ON PRIMARY DGBROKER: SHOW STANDBY DB STATUS.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/a3ab95f4-b576-4926-8cb0-f9b4054be051)

ON PRIMARY DGBROKER: SHOW STANDBY DB STATUS.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/9760435f-1797-4bf5-bde7-5714befaeeba)

ON PRIMARY DGBROKER: SHOW PRIMARY DB STATIC CONNECTION IDENTIFIER

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/48412de4-fc5a-40a4-8093-c28563c0db63)

ON PRIMARY DGBROKER: SHOW STANDBY DB STATIC CONNECTION IDENTIFIER

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/061a78f7-5c9c-4099-a9a0-2fb41ad781e4)

ON PRIMARY DGBROKER: SET CORRECT DB STATIC CONNECTION IDENTIFIER

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/22bd81a2-95cd-45ec-ba12-61dc308d043b)

ON PRIMARY: CONNECT WITH DGBROKER.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/d500445a-17bf-41ca-9285-be052051c2d8)

ON PRIMARY DGBROKER: SHOW CONFIGURATION.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/24d0ebbe-66ea-432c-8f71-22a4edbee9e0)

UZMA19C is Primary and SUZMA19C is STANDBY

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/1d450a2e-1b5a-4249-8712-5d17f8b7c509)

ON STANDBY: IT IS NEW PRIMARY.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/a4da031c-81f0-4655-90f6-6f91a7355ec9)

ON PRIMARY: IT IS NEW STANDBY.

![image](https://github.com/The-DBA-world/ORACLE-19c-DG-SWITCHOVER-VIA-DGBROKER/assets/116766530/2d7380c1-124d-419b-976b-f5c50cdaca51)
