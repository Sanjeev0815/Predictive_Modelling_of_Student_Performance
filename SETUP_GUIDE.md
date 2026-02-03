"""
Quick Start Guide
Complete setup instructions for the project
"""

# ============================================================================
# INSTALLATION GUIDE - AI-Driven Student Performance Prediction System
# ============================================================================

## 1. PREREQUISITES

- Python 3.8 or higher
- MySQL Server 5.7+
- Git
- 4GB RAM minimum
- Internet connection (for downloading dependencies)

---

## 2. INSTALLATION STEPS

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/student_performance_ai.git
cd student_performance_ai
```

### Step 2: Create Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Linux/Mac
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Python Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Setup MySQL Database

#### Option A: Using MySQL Command Line
```bash
# Login to MySQL
mysql -u root -p

# Create database and tables
source database/schema.sql

# Verify tables created
SHOW TABLES;
```

#### Option B: Using MySQL Workbench
1. Open MySQL Workbench
2. File → Open SQL Script → Select `database/schema.sql`
3. Execute the script

### Step 5: Configure Environment Variables
```bash
# Copy .env template
cp .env.example .env

# Edit .env with your settings
# On Windows: Use Notepad or VS Code
# On Linux/Mac: Use nano or vim

nano .env
```

**Important Configuration:**
```
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_NAME=student_performance_ai
```

### Step 6: Verify Installation
```bash
# Test database connection
python -c "from database.db_connection import DatabaseConnection; print('DB Connected!')"

# Test imports
python -c "import streamlit; import tensorflow; import torch; print('All imports successful!')"
```

---

## 3. RUNNING THE APPLICATION

### Start Streamlit Server
```bash
streamlit run app.py
```

The application will open in your browser at `http://localhost:8501`

### Default Test Accounts
- **Student**: 
  - Email: student@example.com
  - Password: Password123!
- **Faculty**: 
  - Email: faculty@example.com
  - Password: Password123!
- **Admin**: 
  - Email: admin@example.com
  - Password: Password123!

---

## 4. DATA IMPORT

### Load Sample Data
```bash
# Method 1: Using Python script
python scripts/import_sample_data.py

# Method 2: Using MySQL
mysql -u root -p student_performance_ai < data/sample_dataset.sql
```

---

## 5. MODEL SETUP

### Download Pre-trained Models (Optional)
```bash
# If models are not included, download them:
# 1. TensorFlow models - trained_models/academic_model.h5
# 2. LSTM model - trained_models/lstm_model.h5
# 3. Fusion model - trained_models/fusion_model.h5
# 4. BERT model - trained_models/bert_model/

# For now, models will be trained on first run
python scripts/train_models.py
```

---

## 6. PROJECT STRUCTURE

```
student_performance_ai/
├── app.py                    # Main Streamlit app
├── requirements.txt          # Dependencies
├── .env                      # Configuration
├── README.md                 # Documentation
│
├── config/
│   ├── db_config.py
│   └── settings.py
│
├── database/
│   ├── schema.sql
│   ├── db_connection.py
│   └── queries.py
│
├── models/
│   ├── academic_dnn.py
│   ├── semester_lstm.py
│   ├── resume_bert.py
│   ├── certificate_ocr.py
│   ├── career_matcher.py
│   └── fusion_model.py
│
├── services/
│   ├── auth_service.py
│   ├── prediction_service.py
│   └── recommendation_service.py
│
├── utils/
│   ├── preprocessing.py
│   ├── feature_engineering.py
│   ├── explainability.py
│   └── validators.py
│
├── visualizations/
│   ├── dashboards.py
│   └── trend_graphs.py
│
├── trained_models/
│   ├── academic_model.h5
│   ├── lstm_model.h5
│   └── fusion_model.h5
│
└── uploads/
    ├── resumes/
    └── certificates/
```

---

## 7. TROUBLESHOOTING

### Issue: MySQL Connection Error
**Solution:**
```bash
# Check if MySQL is running
# Windows: Services → MySQL
# Linux: sudo systemctl status mysql
# Mac: brew services list

# Verify credentials in .env
# Test connection: python -c "import mysql.connector; ..."
```

### Issue: ModuleNotFoundError
**Solution:**
```bash
# Ensure virtual environment is activated
which python  # Should show path in venv

# Reinstall dependencies
pip install --upgrade -r requirements.txt
```

### Issue: Streamlit Not Starting
**Solution:**
```bash
# Clear Streamlit cache
streamlit cache clear

# Try running with explicit host
streamlit run app.py --server.address localhost --server.port 8501
```

### Issue: CUDA/GPU Not Detected (TensorFlow)
**Solution:**
```bash
# For CPU-only (recommended if no GPU):
pip install tensorflow-cpu

# For GPU support:
pip install tensorflow-gpu
```

---

## 8. PRODUCTION DEPLOYMENT

### Using Gunicorn (Backend API)
```bash
gunicorn -w 4 -b 0.0.0.0:5000 app:server
```

### Using Docker
```bash
# Build image
docker build -t student-ai .

# Run container
docker run -p 8501:8501 student-ai
```

### Using Heroku
```bash
heroku login
heroku create student-performance-ai
git push heroku main
```

---

## 9. SECURITY CHECKLIST

- [ ] Change all default passwords
- [ ] Update SECRET_KEY in .env
- [ ] Enable HTTPS
- [ ] Configure firewall rules
- [ ] Set up database backups
- [ ] Enable audit logging
- [ ] Configure email alerts
- [ ] Set up monitoring

---

## 10. PERFORMANCE OPTIMIZATION

### Database Optimization
```sql
-- Add indexes
CREATE INDEX idx_gpa ON academics(gpa);
CREATE INDEX idx_attendance ON attendance(attendance_percentage);
```

### Model Optimization
- Use model quantization for faster inference
- Implement caching for predictions
- Use batch processing for bulk operations

### Streamlit Optimization
```python
@st.cache_data
def expensive_computation():
    pass
```

---

## 11. MONITORING & LOGS

### View Application Logs
```bash
# Streamlit logs
cat ~/.streamlit/logs/

# Application logs
tail -f logs/app.log
```

### Database Monitoring
```sql
-- Check slow queries
SET GLOBAL slow_query_log = 'ON';
SET GLOBAL long_query_time = 2;
```

---

## 12. MAINTENANCE

### Weekly Tasks
- [ ] Check disk space
- [ ] Review error logs
- [ ] Validate predictions accuracy
- [ ] Update model performance metrics

### Monthly Tasks
- [ ] Database optimization
- [ ] Security audit
- [ ] Performance review
- [ ] Backup verification

---

## 13. SUPPORT & DOCUMENTATION

- **Documentation**: See README.md
- **API Reference**: See docs/api.md
- **Database Schema**: See docs/database.md
- **Model Details**: See docs/models.md

---

## 14. NEXT STEPS

1. Complete installation and setup
2. Load sample data
3. Train models (if needed)
4. Test with sample data
5. Configure email notifications
6. Set up monitoring
7. Deploy to production

---

**Need Help?**
- Check GitHub Issues
- Read comprehensive documentation
- Contact support team

**Version**: 1.0.0  
**Last Updated**: February 2026
