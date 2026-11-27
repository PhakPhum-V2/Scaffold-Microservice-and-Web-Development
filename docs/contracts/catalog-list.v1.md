# API รายการสินค้า
สถานะ: PROPOSED
รุ่น: v1
เจ้าของข้อเสนอ: Microservice

คำขอ: GET /api/v1/catalog/products
Request body: ไม่ส่ง
Query: available เลือกใส่ได้ รับ true หรือ false

ผลquery : 

available=true 
{
  "data": [
    { "id": "pencil", "name": "ดินสอ", "priceSatang": 1200, "available": true },
    { "id": "eraser", "name": "ยางลบ", "priceSatang": 800, "available": true }
  ]
}

available=false 
{
  "data": [
    { "id": "ruler", "name": "ไม้บรรทัด", "priceSatang": 2000, "available": false }
    { "id": "sharpener", "name": "กบเหลาดินสอ", "priceSatang": 2000, "available": false },
  ]
}

ailable=yes
{
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Invalid query parameter",
    "details": [
        { "field": "available", "reason": "must be 'true' or 'false'" }
    ]
  }
}


ไม่ส่ง query
{
  "data": [
    { "id": "pencil", "name": "ดินสอ", "priceSatang": 1200, "available": true },
    { "id": "ruler", "name": "ไม้บรรทัด", "priceSatang": 2000, "available": false },
    { "id": "eraser", "name": "ยางลบ", "priceSatang": 800, "available": true },
    { "id": "ruler", "name": "ไม้บรรทัด", "priceSatang": 2000, "available": false }
  ]
}


