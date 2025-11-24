# Telecom Customer Segmentation Using K-Means & Power BI  
*A full end-to-end analytics, feature engineering, and clustering project inspired by MTN subscriber behavior.*

---

## Project Overview

This project builds a **telecom customer segmentation model** using synthetic MTN-style subscriber data (40,000 records).  
It includes:

- Feature engineering based on real telecom KPIs  
- Scaling and log transforms  
- K-Means clustering (k = 4)  
- PCA-based validation  
- A professional **Power BI dashboard** for business insights  
- A reusable customer segmentation pipeline for production

The goal is to demonstrate how telecom operators can segment subscribers for:

- targeted marketing  
- ARPU growth  
- network planning  
- churn prevention  
- product personalization  

---

## 🎯 Business Problem

Telecom operators manage millions of subscribers with very different behaviors.  
Without segmentation, marketing and network planning become:

- inefficient  
- expensive  
- poorly targeted  
- reactive instead of proactive  

This project shows how **machine learning-based segmentation** helps understand subscriber clusters such as:

- heavy data streamers  
- low-usage customers  
- night surfers  
- voice-centric users  

and how these insights drive commercial and network decisions.

---

## Dataset Description

A synthetic dataset representing mobile subscriber behavior.  
It includes usage, recharge, and network-related attributes commonly used in telecom analytics.

### **Raw Columns**
| Column | Meaning |
|--------|---------|
| monthly_data_mb | Total monthly data consumed |
| monthly_voice_minutes | Total call minutes |
| monthly_sms | Number of SMS sent |
| recharge_amount | Total recharge value per month |
| recharge_count | Recharge frequency |
| night_data_mb | Data used between 12am–6am |
| peak_data_mb | Data used during peak hours |
| weekend_usage_ratio | Weekend-to-weekday usage ratio |
| num_failed_calls | Count of failed call attempts |

### **Engineered Features**
These reflect real telecom behavioral metrics:

- `night_ratio`  
- `peak_ratio`  
- `usage_intensity`  
- `voice_data_ratio`  
- `weekday_usage_ratio`  

These features significantly improve clustering accuracy.

---

## Machine Learning Approach

### **1. Data Preparation**
- Outlier handling  
- Log transforms for skewed columns  
- Feature engineering  
- Train-test consistency handling  
- Scaling with StandardScaler

### **2. Clustering**
- K-Means clustering  
- Elbow method (optimal k = 4)  
- Silhouette score (0.37 — strong for behavioral data)

### **3. PCA Validation**
A 2-component PCA projection confirms clear cluster separation.

---

## Final Segments Identified

### **Cluster 0 — High-Value Heavy Data Streamers**
- Extremely high data consumption  
- High peak-hour usage  
- High ARPU customers  
- Primary targets for 4G/5G upgrades  

### **Cluster 1 — Low-Usage Casual / Dormant Users**
- Lowest usage across all categories  
- Minimal monthly recharge activity  
- Most churn-prone segment  

### **Cluster 2 — Night Surfers / Value Seekers**
- High night-time usage  
- Low ARPU but high data efficiency  
- Respond strongly to discounted night bundles  

### **Cluster 3 — Voice-Centric Traditional Users**
- Heavy voice callers  
- Frequent rechargers  
- Network quality issues (failed calls)  
- Strong candidates for VoLTE upgrades  

---

## Power BI Dashboard

A one-page executive-friendly dashboard that includes:

- Total Subscribers  
- Average ARPU  
- Highest ARPU Segment  
- Highest Usage Segment  
- Segment Distribution (Donut Chart)  
- ARPU by Segment (Bar Chart)  
- Data Usage by Segment  
- Voice Minutes by Segment  
- Full Segment Interpretations  

### Dashboard Files
- **PDF Export**  
- **High-resolution screenshots**  

(Stored in the `dashboard/` folder.)

---

##  Reusable Segmentation Pipeline

A complete Python pipeline is included that allows you to:

- load new subscriber batches  
- engineer features  
- scale using the saved scaler  
- assign clusters with the trained K-Means model  
- append segment names  


