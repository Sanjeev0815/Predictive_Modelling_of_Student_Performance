"""
INSTALLATION & USAGE CHECKLISTS
"""

# ============================================================================
# ✅ PRE-INSTALLATION CHECKLIST
# ============================================================================

BEFORE YOU START:
☐ Python 3.8+ installed
☐ MySQL Server installed and running
☐ Git installed
☐ Internet connection (for dependencies)
☐4GB RAM minimum
☐ 2GB disk space for dependencies

---

# ============================================================================
# 📥 INSTALLATION CHECKLIST
# ============================================================================

STEP 1: SETUP ENVIRONMENT
☐ Clone repository: git clone <repo-url>
☐ Navigate to folder: cd student_performance_ai
☐ Create virtual environment: python -m venv venv
☐ Activate venv: venv\Scripts\activate (Windows) or source venv/bin/activate (Linux/Mac)

STEP 2: INSTALL DEPENDENCIES
☐ Run: pip install -r requirements.txt
☐ Wait for installation to complete (3-5 minutes)
☐ Verify: python -c "import tensorflow; import streamlit; print('OK')"

STEP 3: DATABASE SETUP
☐ Open MySQL: mysql -u root -p
☐ Execute: source database/schema.sql
☐ Verify tables: SHOW TABLES;
☐ Exit: exit

STEP 4: CONFIGURE APPLICATION
☐ Copy .env template
☐ Edit .env file with your credentials
☐ Save configuration

STEP 5: TEST & VERIFY
☐ Test DB connection: python -c "from database.db_connection import DatabaseConnection; print('Connected')"
☐ Test imports: python -c "from models.fusion_model import FusionModel; print('Models OK')"
☐ All tests passed!

---

# ============================================================================
# 🚀 RUNNING THE APPLICATION
# ============================================================================

COMMAND TO START:
streamlit run app.py

WHAT TO EXPECT:
✓ Streamlit server starts on localhost:8501
✓ Browser opens automatically (or visit http://localhost:8501)
✓ Login page appears with demo credentials
✓ System ready to use!

---

# ============================================================================
# 🔐 DEFAULT TEST CREDENTIALS
# ============================================================================

STUDENT LOGIN:
Email: student@example.com
Password: Password123!
Features: Dashboard, Profile, Resume Upload, Predictions, Recommendations

FACULTY LOGIN:
Email: faculty@example.com
Password: Password123!
Features: Student Analytics, Risk Assessment, Reports, Dashboard

ADMIN LOGIN:
Email: admin@example.com
Password: Password123!
Features: User Management, System Logs, Settings

---

# ============================================================================
# 📂 IMPORTANT FILES TO KNOW
# ============================================================================

CONFIGURATION:
- .env ..................... Database and app settings
- config/settings.py ....... Application constants

DATABASE:
- database/schema.sql ...... Create all tables
- database/queries.py ...... Query helpers

CORE APPLICATION:
- app.py ................... Main Streamlit app
- services/prediction_service.py .. Make predictions
- services/recommendation_service.py .. Generate recommendations

MODELS:
- models/fusion_model.py ... Ensemble predictions
- models/academic_dnn.py ... Academic performance
- models/semester_lstm.py .. Trend analysis

DOCUMENTATION:
- README.md ................ Complete documentation
- SETUP_GUIDE.md ........... Detailed setup
- QUICK_REFERENCE.md ....... Quick lookup

---

# ============================================================================
# 🎯 FIRST TIME USER GUIDE
# ============================================================================

1. LOGIN
   ☐ Go to http://localhost:8501
   ☐ Login as student
   ☐ View your dashboard

2. EXPLORE FEATURES
   ☐ Click "Profile" to update your information
   ☐ Click "Upload Resume" to test resume parsing
   ☐ Click "Predictions" to generate prediction
   ☐ Click "Recommendations" to see suggestions
   ☐ Click "Analytics" to view trends

3. TEST PREDICTIONS
   ☐ Navigate to Predictions page
   ☐ Click "Generate Prediction" button
   ☐ View prediction result and confidence score
   ☐ Read explanations and recommendations

4. EXPLORE ANALYTICS
   ☐ View GPA trends
   ☐ See attendance patterns
   ☐ Check peer rankings
   ☐ Review performance breakdown

5. FACULTY DASHBOARD
   ☐ Logout and login as faculty
   ☐ View all student analytics
   ☐ Generate reports
   ☐ Identify at-risk students

---

# ============================================================================
# 🔧 QUICK TROUBLESHOOTING
# ============================================================================

PROBLEM: "ModuleNotFoundError"
SOLUTION:
  1. Verify venv is activated: where python (should show venv path)
  2. Reinstall: pip install --upgrade -r requirements.txt
  3. Restart terminal and application

PROBLEM: "MySQL Connection Error"
SOLUTION:
  1. Check MySQL is running
  2. Verify credentials in .env
  3. Test: mysql -u root -p -e "SELECT 1;"

PROBLEM: "Streamlit Not Starting"
SOLUTION:
  1. Clear cache: streamlit cache clear
  2. Try: streamlit run app.py --logger.level=debug
  3. Check port 8501 is not in use

PROBLEM: "Models Not Loaded"
SOLUTION:
  1. Check trained_models/ folder exists
  2. Models will auto-train on first use
  3. This may take a few minutes

---

# ============================================================================
# 📊 WHAT TO TRY NEXT
# ============================================================================

AFTER SUCCESSFUL INSTALLATION:

1. LOAD SAMPLE DATA
   ☐ Import sample_dataset.csv into database
   ☐ Test predictions on real data

2. CUSTOMIZE FOR YOUR INSTITUTION
   ☐ Update application settings
   ☐ Configure notification emails
   ☐ Add custom career paths

3. TRAIN WITH REAL DATA
   ☐ Collect student data
   ☐ Train models with your data
   ☐ Evaluate model performance

4. SETUP MONITORING
   ☐ Enable logging
   ☐ Setup alerts
   ☐ Monitor predictions

5. DEPLOY TO PRODUCTION
   ☐ Configure security settings
   ☐ Setup HTTPS
   ☐ Deploy using Docker
   ☐ Setup backups

---

# ============================================================================
# 📚 DOCUMENTATION STRUCTURE
# ============================================================================

README.md
├── Features Overview (100 lines)
├── System Architecture (50 lines)
├── Model Details (80 lines)
├── Database Schema (60 lines)
├── Installation (40 lines)
├── API Endpoints (50 lines)
└── Troubleshooting (50 lines)

SETUP_GUIDE.md
├── Prerequisites
├── Step-by-step Installation
├── Data Import
├── Model Setup
├── Troubleshooting
├── Production Deployment
├── Security Checklist
└── Maintenance

QUICK_REFERENCE.md
├── 5-minute Quick Start
├── File Purposes
├── Common Tasks
├── Database Queries
├── Commands
└── Support Resources

---

# ============================================================================
# 🎓 LEARNING PATH
# ============================================================================

BEGINNER (Hours 1-2):
1. Read README.md - Understand features
2. Run SETUP_GUIDE.md - Complete installation
3. Start application
4. Explore student dashboard
5. Try making a prediction

INTERMEDIATE (Hours 3-6):
1. Review code structure
2. Understand database schema
3. Study model implementations
4. Test API endpoints
5. Try customizations

ADVANCED (Hours 7+):
1. Train models with custom data
2. Implement new features
3. Deploy to production
4. Setup monitoring
5. Optimize performance

---

# ============================================================================
# 🚀 QUICK START (3 STEPS)
# ============================================================================

STEP 1 - INSTALL (5 minutes)
```bash
pip install -r requirements.txt
mysql < database/schema.sql
```

STEP 2 - CONFIGURE (2 minutes)
```bash
Edit .env with database credentials
```

STEP 3 - RUN (1 minute)
```bash
streamlit run app.py
```

DONE! Access at http://localhost:8501

---

# ============================================================================
# ✨ FEATURES READY TO USE
# ============================================================================

✅ Student Performance Prediction
✅ Resume Parsing & Analysis
✅ Career Path Recommendations
✅ Academic Trend Analysis
✅ Risk Detection
✅ Personalized Recommendations
✅ Peer Benchmarking
✅ Interactive Dashboards
✅ Multi-role Access Control
✅ Data Visualization
✅ Comprehensive Reporting
✅ Secure Authentication

---

# ============================================================================
# 📞 NEED HELP?
# ============================================================================

1. Check README.md for features
2. See SETUP_GUIDE.md for installation issues
3. Review QUICK_REFERENCE.md for common tasks
4. Check code comments for implementation details
5. Review error logs in logs/ folder
6. Contact support via GitHub issues

---

**Version**: 1.0.0
**Status**: ✅ Production Ready
**Last Updated**: February 2026

🎉 Thank you for using this system! 🎉
