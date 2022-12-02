# MacOS-TimeMachine
About MacOS Time Machine Setting

## Using Windows NFS to backup with TimeMachine

1. สร้างแชร์ Folder บน Windows

![windows-share-folder](https://user-images.githubusercontent.com/56244402/205286436-822e5b57-bc0e-46f7-b0a0-76bf2068f59c.JPG)

2. จากนั้นที่เครื่อง Mac ไปที่ Finder -> Connect to Server

<img width="598" alt="Screenshot 2565-12-02 at 18 51 40" src="https://user-images.githubusercontent.com/56244402/205287114-4a997ffc-eade-4de4-96a0-b3238f28301d.png">

3. เปิด Terminal แล้วใช้คำสั่ง (ในภาพ - ให้เข้าไปในโฟลเดอร์ที่แชร์ก่อน) เพื่อสร้างไฟล์จำลอง Disk ชนิด HFS ซึ่งใช้สำหรับระบบ TimeMachine เราสามากำหนดขนาดของพื้นที่ที่จะใช้ในการ Backup ได้ (ตามตัวอย่างจะใช้ขนาด 650GB) ซึ่งแนะนำให้สร้างขนาดเป็นสองเท่าของ Disk บนเครื่อง Mac ที่เราใช้อยู่ (ไม่ถึงก็ได้แต่อย่าให้ต่ำกว่า) และกำหนดพื้นที่ปลายทางสำหรับการ Backup ไปยังโฟลเดอร์ NFS ที่เราแชร์ไว้

![image](https://user-images.githubusercontent.com/56244402/205288737-2c49e863-dbfd-48d4-ba8e-f9d4226ff622.png)

4. เข้าไป Mount File 'TimeMachine.sparsebundle' ด้วยการคลิกขวาที่ไฟล์ แล้วเปิดด้วย DiskImageMounter -> เมื่อสำเร็จให้เปลี่ยนชื่อ Disk เป็น TimeMachine

<img width="839" alt="Screenshot 2565-12-02 at 19 03 44" src="https://user-images.githubusercontent.com/56244402/205289253-c9eb6167-5f76-45cf-928c-8f43b1c73358.png">

5. กำหนดพื้นที่ปลายทางสำหรับ TimeMachine ไปยัง Disk ที่เรา Mount จากข้อ 4. (หากมี Error แบบในภาพให้เข้าไป Full Disk Access ให้กับ terminal ใน setting -> Security & Privacy

![image](https://user-images.githubusercontent.com/56244402/205289575-6f61ab79-f269-49f7-9a77-fd53bf31c68f.png)

6. ไปที่ Setting -> TimeMachine จะเห็น Disk TimeMachine แสดงขึ้นมา ให้คลิกขวาแล้วเริ่ม 1st Time Full Backup ได้เลย

<img width="827" alt="Screenshot 2565-12-02 at 16 57 19" src="https://user-images.githubusercontent.com/56244402/205289943-fbf0330d-6904-40f0-bb2e-57ed2c6f5a9b.png">

7. สร้าง AppleScript สำหรับทำให้ Auto Mount NFS TimeMachine Folder ทุกครั้งที่เราเปิดเครื่อง ให้เปิด App Script (มีมาให้พร้อม MacOS) ขึ้นมาแล้วเขียนตามภาพ

<img width="812" alt="Screenshot 2565-12-02 at 17 55 42" src="https://user-images.githubusercontent.com/56244402/205290715-72aa8b29-c22d-4f24-b100-9f6e967c7b86.png">

8. สุดท้ายนำ Script ที่สร้างไว้ไปใน Login Items ของเรา

<img width="827" alt="Screenshot 2565-12-02 at 19 12 12" src="https://user-images.githubusercontent.com/56244402/205290928-bebad750-a101-4c0f-baa7-a69b22fa09db.png">
