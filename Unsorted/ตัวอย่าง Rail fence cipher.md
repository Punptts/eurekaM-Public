**AW 1 (Main cover)**
EP 2:  Rail fence cipher  
ถอดรหัสไปกับhashpire

**AW 2**
What is Rail fence cipher ?
Rail fence cipher (zigzag cipher) คือ การเข้ารหัสแบบ Transposition cipher โดยการนำข้อความธรรมดาไปเขียนลงในตารางตามเเนวทเเยงต่อเนื่องกันบนลงล่างเเละล่างขึ้นบน ซึ่งมีรูปแบบเปรียบเสมือนเป็นรั้วและรางที่เชื่อมต่อกัน

**AW 3 (cover - encrypt)**
ขั้นตอนการเข้ารหัสแบบ Rail fence cipher

**AW 4*
1.  กำหนดข้อความที่ต้องการเข้ารหัส เป็น WE ARE DISCOVERED FLEE AT ONCE
    
2.  กำหนดคีย์ ในที่นี้ คือการกำหนดจำนวนแถว อย่างในรูปที่ 1 เป็นแบบ 3 แถว ส่วนคอลัมน์ จะคำนวณคอลัมน์จาก จำนวนของตัวอักษรในข้อความที่ต้องการเข้ารหัสได้เป็น 25 คอลัมน์

**AW 5**
3. นำข้อความไปใส่ลงในตาราง ตามแนวทแยงเริ่มจากด้านซ้ายบนลงล่างและล่างขึ้นบนจนครบ ดังรูปที่ 1
	-- รูป--

**AW 6**
4.  นำตัวอักษรในตารางมาเรียงต่อกัน โดยเรียงจากซ้ายไปขวาตามเเต่ละแถว(ราง) จะเข้ารหัสได้เป็น WECRL TEERD SOEEF EAOCA IVDEN
    
5.  ในการเข้ารหัสลับ เราสามารถเขียนรหัสเรียงติดกัน โดยไม่ต้องเว้นช่องว่างได้ แต่เพื่อให้ง่ายต่อการจำและการเขียน ส่วนใหญ่ จึงเขียนเป็นกลุ่มตัวอักษร กลุ่มล่ะ 5 ตัว จำนวนกลุ่มขึ้นอยู่กับจำนวนของตัวอักษรทั้งหมด

**AW 7 (cover - decrypt)**
1. คีย์ และ รหัสลับ

**AW 8**
2.  ทำการสร้างตารางขึ้นมา โดยให้คีย์เป็นตัวกำหนดจำนวนแถว และจำนวนตัวอักษรในรหัสลับเป็นตัวกำหนดจำนวนคอลัมน์
    
3.  นำตัวอักษรตัวแรกในรหัสลับไปใส่ไว้ในตารางที่มุมบนด้านซ้าย จากนั้นให้ทำการขีดเส้นทแยงเรียงจากบนลงล่าง และล่างขึ้นบนจนครบ ดังรูปที่ 2
	-- รูป--

**AW 9**
4. นำรหัสลับ WECRL TEERD SOEEF EAOCA IVDEN ใส่ลงในตาราง ตามช่องที่ได้ขีดเส้นไว้ ดังรูปที่ 3
	-- รูป--
5. ใส่รหัสลงในตารางจนครบ จะได้ดังรูปที่ 4
	-- รูป--

**AW 10**
	-- รูป--
6. นำตัวอักษรในตารางมาเรียงต่อกัน โดยเรียงตามแนวทแยงบนลงล่างและล่างขึ้นบน จะได้ข้อความ คือ WE ARE DISCOVERED FLEE AT ONCE
