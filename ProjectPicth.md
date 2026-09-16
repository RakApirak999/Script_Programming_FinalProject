# Final Term Project Pitch

## 1. Project Title

**Smart Travel Planner — ระบบช่วยวางแผนการท่องเที่ยวอัจฉริยะ**

---

## 2. Problem Statement

การวางแผนท่องเที่ยวด้วยตนเองต้องค้นหาข้อมูลจากหลายแหล่ง เช่น สภาพอากาศ สถานที่ท่องเที่ยว และข้อมูลสถานที่ ทำให้ใช้เวลานานและอาจวางแผนกิจกรรมไม่เหมาะสมกับสภาพอากาศในแต่ละวัน

---

## 3. Proposed Solution

Smart Travel Planner เป็นแอปพลิเคชันที่ช่วยผู้ใช้วางแผนการท่องเที่ยว โดยรับเมืองหรือสถานที่ปลายทางจากผู้ใช้ แล้วเรียกข้อมูลจาก API เพื่อแสดงข้อมูลสภาพอากาศและข้อมูลสถานที่ท่องเที่ยว จากนั้นผู้ใช้สามารถเลือกสถานที่ที่สนใจและบันทึกแผนการเดินทางไว้ในฐานข้อมูล SQLite เพื่อเรียกดูและแก้ไขแผนการเดินทางภายหลังได้

---

## 4. Domain

**Daily App / Network App / Data Analysis & Management**

---

## 5. API(s) to Use

### API 1: OpenWeatherMap API

* **Documentation Link:** https://openweathermap.org/api
* **Type of Data:** Weather data เช่น temperature, humidity, weather condition และ forecast

### API 2: Geoapify Places API

* **Documentation Link:** https://www.geoapify.com/places-api/
* **Type of Data:** ข้อมูลสถานที่ เช่น สถานที่ท่องเที่ยว ร้านอาหาร พิพิธภัณฑ์ และสถานที่สำคัญ

---

## 6. Data Persistence Plan

**Mini database (SQLite)**

ระบบจะใช้ SQLite สำหรับจัดเก็บข้อมูลที่ผู้ใช้บันทึก เช่น

* ข้อมูลแผนการเดินทาง
* จุดหมายปลายทาง
* วันที่เดินทาง
* สถานที่ท่องเที่ยวที่เลือก
* ลำดับสถานที่ในแผน
* หมายเหตุของผู้ใช้

ข้อมูลจาก API จะถูกนำมาใช้แสดงผลและสามารถบันทึกข้อมูลที่ผู้ใช้เลือกไว้ในฐานข้อมูล

---

## 7. Framework Style

**OOP (Object-Oriented Programming)**

ตัวอย่าง Class ที่ใช้ในระบบ:

* `WeatherAPIClient` — ติดต่อ OpenWeatherMap API
* `PlacesAPIClient` — ติดต่อ Places API
* `Trip` — จัดการข้อมูลแผนการเดินทาง
* `Place` — จัดการข้อมูลสถานที่
* `DatabaseManager` — จัดการ SQLite
* `TravelPlanner` — จัดการ Business Logic ของระบบ

---

## 8. Roles & Responsibilities

### Project Manager / CI-CD Integrator

รับผิดชอบการสร้าง GitHub Repository, จัดการ Branch, GitHub Actions และติดตามความคืบหน้าของโปรเจกต์

### Automated Tester & QA

รับผิดชอบเขียน Unit Test ด้วย pytest, ทดสอบ API และ Database รวมถึงตรวจสอบ Code Quality และ PEP 8

### Core Developer(s)

รับผิดชอบพัฒนา Business Logic, เชื่อมต่อ API, จัดการข้อมูล และพัฒนาระบบ SQLite

---

## 9. Features (MVP)

### 1. Search Destination

ผู้ใช้สามารถค้นหาเมืองหรือจุดหมายปลายทางที่ต้องการเดินทาง

### 2. View Weather & Places

ระบบเรียกข้อมูลจาก API และแสดงสภาพอากาศพร้อมสถานที่ท่องเที่ยวที่น่าสนใจในพื้นที่นั้น

### 3. Create & Save Travel Plan

ผู้ใช้สามารถเลือกสถานที่ กำหนดวันที่ และบันทึกแผนการเดินทางลง SQLite

---

## 10. Stretch Features (Optional)

* ค้นหาและจัดเรียงสถานที่ตามประเภทหรือความสนใจ
* แสดงแผนการเดินทางแยกตามแต่ละวัน
* แนะนำกิจกรรมตามสภาพอากาศ
* แสดงระยะทางระหว่างสถานที่
* แสดงกราฟสรุปข้อมูลการเดินทาง
* Export Travel Plan เป็นไฟล์ PDF
* เพิ่มระบบ Favorites สำหรับสถานที่ที่ผู้ใช้สนใจ

---

## 11. Evaluation Checklist

* [x] API works — ใช้ GET request และมี Error Handling
* [x] JSON data parsing
* [x] Data persisted correctly using SQLite
* [x] Code follows PEP 8
* [x] Unit tests using pytest
* [x] API mocking สำหรับการทดสอบ
* [x] Database testing
* [x] CI/CD pipeline using GitHub Actions
* [x] README includes setup and usage instructions
* [x] Team roles documented
