uplinks:: [[+ HOME]]
tags:: #type/thing❖  #status/boat🚤 #on/summary

# HD Wallet - sum by me
---
## Jot down...
### Blockchain Wallets
-   เปรียบเทียบเหมือนกับ data based ที่มี characteristic ที่พิเศษ ใช้ cryptography ในการ autenticate - private key บอกว่าเราเป็นเจ้าของ
-   Blockchain wallet ไม่ได้มีไว้เก็บ cryptocurrencies แต่มีไว้เก็บ key ในการ access เข้าไปในกระเป๋าตังของเราที่อยู่ใน blockchain
-   Blockchain wallet คือ sofeware แอปพลิเคชัน หรือในเชิง physical คือเป็นกระเป๋าตังแบบ hardware เป็นอุปกรณ์อิเล็กทอนิกอย่างหนึ่ง
-   หน้าที่ของ blackhain wallet มีหน้าที่
    1.  ทำหลักๆ 3 อย่าง gen key, storage, use
    2.  interact กับ เครือข่าย blockchain
-   ประเภทของ wallet
    -   By key location: พูดถึงที่ที่ใช้เก็บ key
        -   Software wallets
        -   Offline wallets: hardware wallet, paper wallet, brain wallet (ง่ายๆคืออะไรที่ใช้ในการช่วยจดจำ key นั่นเอง)
        -   Hosted wallets
    -   By Generation Algorithm
        -   Non-deterministic Wallet
        -   Deterministic wallet
        -   HD Wallets
-   ถ้าอยากให้เงินอยู่ที่เราจริงๆคือเราต้องเป็นเจ้าของ private key การสร้าง wallet ข้างนอกเองถึงดีกว่า / ถ้าอยู่ใน wallet ใน binance ก็เหมือนยอดเงินใน บช ธนาคาร

### Need of multiple key (ทำไมต้องมีหลาย key ?)

-   Blockchain wallet ค่อนข้างต่างจาก bank acc ที่มีแค่ไม่กี่เลข บช ต่อหนึ่งคน ในเชิงของ blockchain wallet สามารถมีกี่ key and address เท่าไหร่ก็ได้ ยิ่งมีเยอะยิ่งปลอดภัยต่อทั้งตัวเราและคนที่ทำ transaction กับเรา
-   ประโยชน์ของการมี multiple key
    -   Privary purpose
        -   Pseudonymous ≠ Annoynymous - หลายๆคนเข้าใจว่าการทำ transaction บน blockchain นั้นปลอดภัยเพราะว่าไม่มีใครสามารถรู้ตัวตนของเราได้ ก็จริงอยู่แต่การทำ transaction สิ่งหนึ่งที่ยังอยู่ (footprint) คือ address หากเราใช้ซ้ำๆ ก็อาจจะทำให้เกิดการสืบค้นข้อมูลจาก address นั้นๆได้ เป็น harm กับตัวเราเองและคนที่ทำ transaction กับเรา
        -   ถ้ามี transaction เยอะๆ บางทีสามารถใช้ ai ในการ analyse ได้ว่าแต่ละ key อาจมี relationship กัน
    -   Security purpose
        -   กันการสุ่ม key จนเจอ - Key rotation (small risk but may happen) การมีหลายๆ key ปล่อยภัยกว่าการใช้ key เดิมซ้ำๆ
        -   ช่วยกรจายความเสี่ยง

---

## Cryptographic Primitives & Math

### Modular Arithmetic

-   Modular or Mod = การหารเอาเศษ
-   คอมพิวเตอร์ทั่วๆไปจะทำงานกับเลขในจำนวนมากๆเกิน maximum ไม่ได้ เพราะฉะนั้นมันจะ wrap up ตัวเลข
-   ตัวอย่าง เช่น
    -   A+B=C — มีตัวแปรทั้งหมด 3 ตัว
    -   8+9=17 — คอมพิวเตอร์จะอ่าน 7 (ใน case ที่ limit max number = 10)
-   Modular = [0,max(n)]
-   7 mod 3 = 1 —> 3x1=3 , 3x2=6 —> เหลือเศษ 1 เพื่อให้ได้ 7
-   เศษ 1 = modulus (หลักๆคือการหารแล้วเลือกใช้เลขที่เป็นเศษ)

### Cryptographic Hash Function

-   Characteristic = Input —> output เป็น one-way จะไม่สามารถเอา output ไปคำนวนหา input ได้ นอกจากจะสามารถสุ่ม input ที่ตรงกับ output
-   Hash function เป็นเหมือนกล่องที่เอาไว้ identify ว่า value ข้างในกล่องคืออะไร เช่น
    -   กล่อง input [message] → กล่อง output [0110101010]
    -   กล่อง input [name] → กล่อง output [0110101010]
    -   สรุปได้ว่ากล่อง input คือ string และกล่อง output คือแปลง string ออกมาเป็นภาษาคอม 0101101010101 → SHA256/SHA512 (ตัวเลขคือระบุจำนวนตัวเลข)

### Eliptical Curve (EC)

-   พูดถึงเรื่อง curve - แต่ละ coin จะมีการใช้ curve ที่แตกต่างกันออกไป
-   แต่ละ chain จะใช้ curve ที่แตกต่างกัน
-   Coin จะมีจุด (x,y) ที่แตกต่างกัน เรียกว่าค่า based point (G) ของ bitcoin คือ (0,7)
-   Main properties
    -   Horizontal symmetric - สมมาตรกันในแนวนอน
    -   Any non-vertical line will intersect at most 3 point - เส้นที่ไม่ใช่เส้น vertical line จะสร้างจุดตัดมากสุด 3 จุดบน curve

### Elliptic Curve Arithmetic (More)

-   Point addition
    -   คือกระบวนการในการเพิ่ม 2 EC points
    -   eg. P + Q
-   Point Scalar Multiplication
    -   คือกระบวนการเพิ่ม points บน curve ไปเรื่อยๆ จนในที่สุดจะได้ point เป็น curve
    -   kP = P + P + P + P...+P

### Blockchain Keys and Addresses

-   ใน Blockchain จะใช้ curve ใช้ในการ generate key
-   Private key: d
    -   คือการสุ่ม positive integer
    -   eg. d = 2022

—> _Point Scalar Multiplication_

-   Public key dG (G = based point of bitcoin)
    -   A point (จุด) ที่อยู่บน EC
    -   eg. dG = 2022G = คูณ G ทั้งหมด 2022 ครั้ง
    -   *ค่า G คืออยู่ที่ว่า coin นั้นใช้ curve อะไร ค่า G คือจุดบน curve หรือ based point

—> Hash & Encode

-   Generate Address: H(dG)
    -   Address คือ hash value ของ public key (หลังจากเอา public key ไปคำนวน hash value)
    -   Encode คือการแปลง value 1001001010 —> ให้เป็นภาษาที่มนุษย์อ่านได้ก็คือ alphabet + number / ถ้าเป็น 011010 อาจทำให้สับสน

### ECC Composite (compose) Property (More)

-   Characteristic นึงของ ECC for example, (a+b)G = ag+bg

---

## HD Wallets

### Non-deterministic Wallet (generate key only)

-   คือรุ่นแรกของ blackchain wallet
-   การ generate key คือแบบสุ่ม จะสุ่มใหม่ทุกครั้งเมื่อมีการนำไปใช้ แต่ละ key ไม่มี relationship กัน
-   Problam - ปัญหา
    -   การสุมทุกครั้งทำให้มีจำนวน key เยอะเกินไป ผู้ใช้ต้องทำการ backup ทุกครั้งทีมีการ gen ใหม่
    -   backup storage size พื้นที่จัดเก็บต้องใหญ่พแที่จะสามารถจัดเก็บได้ทุก key
    -   ไม่รองรับการส่ง key ข้ามระหว่าง device ทำให้ยุ่งยากในการนำไปใช้

### Deterministic (use seed to generate key)

-   KDF - Key derivation function คือที่มาของการ generate key - hash function อย่างหนึ่ง
-   ใช้ seed เพื่อคำนวน private key ออหมาได้ (1 seed สามารถมี private key ได้หลายอัน)
-   Seed ส่วนมากจะ generate ออกมาเป็นภาษาที่มนุษย์สามารถอ่านและเขียนได้ เรียกว่า mnemonic (คือการเรียนรู้ข้อมูลในรูปแบบที่มนุษย์สามารถจำและทำความเข้าใจได้) หรือเรียกกันว่า BIP 39 - ช่วยทำให้การ backup ง่ายขึ้น
-   สามารถทำการ backup เฉพาะ seed ได้เพื่อเก็บ keys ทั้งหมด → 1 seed = all keys

### Deterministic Wallet type 1

-   เป็นรุ่นแรก
-   KDF = Private key(i) = Hash(i//seed//type) มี 3 value ใช้ในการ gen seed และก็สามารถใช้ seed ไป gen key อื่นๆต่อได้
-   Problam - ปัญหา
    -   ถ้า seed หลุดออกไปทุกอย่างก็จะถูกเข้าถึงได้ด้วย
    -   Wallet sharing นั้นจำกัด เพราะ seed เดียวมีหลาย key และการเข้าถึง key ต่างๆต้องผ่าน seed เดียวกันหมด option การแชร์จึงมีแค่ 2 อย่าง 1.share and 2.not-share
    -   ตัวอย่าง หาก server ต้องเข้าถึง key ต่างๆ เราจึงต้องนำ seed ไปใส่ใน server ถ้า server โดน hack = ทุกอย่างอาจเป็นอันตรายได้

### Hierarchical Deterministic Wallet type 2 - BIP32

-   เป็น standard ในการ generate key ที่ใช้อยู่ในปัจจุบัน เช่น metamask and etc.
-   เพิ่ม concept ของ chain code เข้าไปใน Deterministic wallet เพื่อเพิ่ม ตัวแปร ให้สามารถเข้าถึงข้อมูลได้ยากขึ้น ไม่ไปขึ้นอยู่กับ key อย่างเดียว
    -   Generate : Master pricate key, Master public key and Master chaincode
-   If private key pair with public key = they use the same chain code
-   มีทั้งหมด 2 ประเภท
    -   Normal (soft / non-hardened)
        -   ในรูปแบบนี้ parent key จะสามารถใช้ calculate child key ได้
    -   Hardened (hard)
        -   คือการสร้าง key แบบใช้ private key + Chaincode + i ในการ gen I_L
        -   ในรูปแบบนี้จะตรงกันข้าม parent key จะไม่สามารถใช้ calculare public child key ได้
        -   ใช้เพื่อเพิ่มความปลอดภัยในระบบ เช่น layer ไหนที่ไม่จำเป็นต้อง calculate child key ก็จะถูกสร้างในรูปแบบของ hardenned
-   Extended Private key = chain code + private key
-   Extended Public key = chain code + public key

### Use case of Hierarchical Tree

-   Can be use in manage key for organization structure สามารถ apply ได้ใน organization structure การ generate key ให้แต่ละ department เพื่อ control access
-   key ที่สูงกว่าจะสามารถใช้ calculate child key + สามารถ access child key ได้

---

## CPK Wallets (more)
-   การทำงานของกระเป๋าตัง CPK
    -   Private sequence [private key1, private key2, private key3] → calculate → master private key
    -   เหมือนกับ Private key + chain code → master private key
-   หลักๆคือเพิ่ม concept ของ sequence เข้าไป
-   ยิ่ง sequence ยาวก็จะยิ่งปลอดภัย calculate ยาก ในทางกลับกันถ้า sequence น้อย จะ calculate ได้เร็ว และปลอดภัยน้อยกว่า

---
## Resources
- x
