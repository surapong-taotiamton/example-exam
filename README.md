# จงตอบคำถามต่อไปนี้โดยกรุณาเขียนตัวบรรจง

1. Polymorphism คืออะไร มีประโยชน์อย่างไร

1. Dependency injection คืออะไร มีประโยชน์อย่างไร

1. จงอธิบายว่า MVC คืออะไร M คืออะไร , V คืออะไร , C คืออะไร มีประโยชน์อย่างไร

1. Race condition คืออะไร และมีวิธีแก้ไขอย่างไร

1. จงอธิบายว่า Data structure เหล่านี้เก็บข้อมูลอย่างไรและมีข้อดีข้อเสียอย่างไร
    * Link List
    * Array
    * Binary tree
    * Hash

1. กระบวนการ Transaction ของ Database คืออะไร มีไว้ทำไม ข้อดีของมันคืออะไร ข้อเสียคืออะไร

1. Pass by value กับ Pass by reference คืออะไร แตกต่างกันอย่างไร


1. จงอธิบาย Annotation ของ Spring boot ต่อไปนี้ว่ามีไว้ทำอะไร
    * @Controller
    * @Autowired
    * @RequestMapping

1. จงเขียน Program เพื่อแก้ปัญหาต่อไปนี้  (เขียนภาษาใดก็ได้ pseudo code ก็ได้ และไม่จำเป็นต้อง syntax ถูกต้องร้อยเปอร์เซ็น ขอแค่เขียนแล้วเข้าใจว่ากำลังทำอะไร )

    ```txt
    มีเงิน k บาท มีของ n ชิ้นราคา b1, b2, ..., bn จะซึ้อของให้เงินหมดพอดี
    (ไม่เหลือและไม่ขาด) ได้หรือไม่ ถ้าได้ ได้ราคาเท่าใดบ้าง (หาทุกค่าที่ซื้อได้)

    นั่นคือ B = { b1, b2, ..., bn } เป็น set ของ integers ที่มีค่าซ้ำได้มี
    subset ของ B หรือไม่ที่ sum ของสมาชิกทั้งหมด = k พอดี ของราคาเท่ากันถือเป็นคนละอันกัน 

    ตัวอย่าง Input 

    k = 20, B = {20, 10, 5, 5, 3, 2, 20, 10 }

    Output
    20
    10 5 5
    10 5 3 2
    10 5 3 2
    10 10
    5 5 10
    5 3 2 10
    5 3 2 10
    20
    ```

1. จงเขียน Controller ของ Spring และส่วนที่เกี่ยวข้องเช่น Repository, Model, Bean แล้วแต่ความจำเป็น เพื่อรองรับความต้องการนี้

    ```txt
    ต้องการสร้าง web api ที่ path : /api/idol/getinfo โดยใช้ Http method POST โดย Request body มีรูปแบบดังนี้

    Request body : {
        name : "",   // string
    }

    จากนั้นนำ name ที่อยู่ใน Request body ไปหาข้อมูลใน Database ที่ Table ชื่อ idol โดยมีโครงสร้างดังต่อไปนี้

    Field           Type            Key
    id              bigint(20)      PRI
    name	        varchar(255)
    date_of_birth	date	
    band_name       varchar(255)

    โดยเงื่อนไขการค้นหาคือ name จาก Request body ต้องตรงกับ name ใน table : idol

    จากนั้นนำค่าที่ได้ส่งกลับไปให้ Client โดย โดย Response มีรูปแบบดังนี้

    Response body : {
        code : "", // type string ในกรณี Success =  0 กรณีไม่สำเร็จ = 500
        message : "", // type string ในกรณี Success = "success" กรณีไม่สำเร็จ = "error : " + เหตุผลที่ทำให้เกิด error
        data : [{
            id : "",   // integer
            name : "" // string
            dateOfBirth  : "" // Date,
            bandName : "" // string
        }]  // Array ของ Object ที่ได้มาจาก Database
    }

    ```