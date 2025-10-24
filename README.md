# 🏦 BankGuard AI  
**Predict to Protect — คาดการณ์ก่อน เพื่อรักษาลูกค้าที่สำคัญไว้กับธนาคาร**  

---

## 📘 Overview  
BankGuard AI เป็นโปรเจกต์ Machine Learning ที่พัฒนาเพื่อช่วยธนาคาร **คาดการณ์แนวโน้มการลาออกของลูกค้า (Customer Churn Prediction)**  
โดยใช้ข้อมูลลูกค้าธนาคารกว่า 10,000 รายจากชุดข้อมูล **Bank Customer Churn Dataset**  

เป้าหมายของโปรเจกต์คือ  
> "ใช้พลังของ AI เพื่อให้ธนาคารเข้าใจลูกค้าได้ลึกขึ้น และรักษาความสัมพันธ์กับลูกค้าที่มีค่าก่อนที่จะสายเกินไป" 💚  

---

## 🧩 Dataset Information  
- 📊 **Source:** Bank Customer Churn Dataset (Kaggle)  
- 🧮 **Records:** ~10,000 customers  
- 🔢 **Features:** 14 columns  
- 🎯 **Target:** `Exited` →  
  - `1` = ลูกค้าลาออก  
  - `0` = ยังอยู่กับธนาคาร  

---

## ⚙️ Model Development  
โมเดลที่ใช้: **Random Forest Classifier**  
- 🎯 Accuracy ≈ **86%**  
- 📈 Precision ≈ **83%**, Recall ≈ **78%**, F1-Score ≈ **80%**  
- 🔍 Feature สำคัญที่มีผลต่อการลาออก:
  1. Age  
  2. Balance  
  3. IsActiveMember  
  4. CreditScore  
  5. NumOfProducts  

---

## 📊 Exploratory Data Analysis (EDA)
- ลูกค้าส่วนใหญ่มาจาก **France (~50%)**  
- ลูกค้าประเทศ **Germany** มีอัตราการลาออกสูงสุด (~32%)  
- เพศชายมากกว่าเล็กน้อย แต่เพศหญิงมีแนวโน้มลาออกมากกว่า  
- อายุเฉลี่ยของลูกค้าคือ **38 ปี**  
- ระยะเวลาที่อยู่กับธนาคารเฉลี่ย **5 ปี**

---

## 🧠 Advanced Technique: Survival Analysis  
เราใช้เทคนิค **Cox Proportional Hazards Model** เพื่อวิเคราะห์ “ช่วงเวลาที่ลูกค้ามีแนวโน้มลาออก”  
- พบว่าช่วง **ปีที่ 4–6** คือจุดที่ลูกค้ามีโอกาสลาออกสูง  
- ปัจจัยที่เพิ่มความเสี่ยงในการลาออก ได้แก่  
  - ไม่ Active  
  - ยอดเงินคงเหลือสูง  
  - อายุที่มากขึ้น  

---

## 💻 Streamlit Web App Prototype  
ชื่อ: **BankGuard AI App**  
แอปนี้ช่วยให้เจ้าหน้าที่ธนาคารสามารถกรอกข้อมูลลูกค้า  
แล้วระบบจะทำนายว่า  
- ⚠️ “ลูกค้ารายนี้มีแนวโน้มลาออก”  
- ✅ “ลูกค้ารายนี้มีแนวโน้มอยู่ต่อ”  

### 🔧 วิธีรันแอป:
```bash
streamlit run app.py
