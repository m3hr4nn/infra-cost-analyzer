# 🔍 Infrastructure Cost Analyzer

A powerful web-based tool for analyzing cloud infrastructure costs and providing intelligent optimization recommendations. Upload your cloud billing files and get actionable insights to reduce your cloud spending.

![Infrastructure Cost Analyzer](https://img.shields.io/badge/Status-Live-brightgreen) ![License](https://img.shields.io/badge/License-MIT-blue) ![Cloud Support](https://img.shields.io/badge/Cloud-AWS%20%7C%20Azure%20%7C%20GCP-orange)

## 🚀 Live Demo

**Try it now:** [https://m3hr4nn.github.io/infra-cost-analyzer/](https://m3hr4nn.github.io/infra-cost-analyzer/)

Click the **"🎮 Try Demo Data"** button to see the analyzer in action with sample data!

## ✨ Features

### 📊 **Multi-Cloud Analysis**
- **AWS** - Cost and Usage Reports, Billing CSV exports
- **Azure** - Cost Management exports, Usage details
- **Google Cloud** - Billing exports, BigQuery data
- **Auto-Detection** - Automatically identifies provider format

### 🎯 **Smart Analytics**
- Interactive cost visualization with Chart.js
- Service-wise cost breakdown
- Regional spending analysis
- Usage pattern identification
- Trend analysis across time periods

### 💡 **AI-Powered Recommendations**
- Service optimization suggestions
- Resource rightsizing recommendations
- Multi-region consolidation advice
- Cost monitoring best practices
- Potential savings calculations

### 🔒 **Privacy-First**
- **100% Client-Side Processing** - Files never leave your browser
- **No Server Required** - Perfect for GitHub Pages
- **No Data Storage** - Analysis happens in real-time

## 📁 Supported File Formats

### 🟠 **AWS Billing Files**

#### Standard CSV Format (Cost and Usage Report)
```csv
Service,Cost,Date,Region,Usage,ResourceId
EC2-Instance,156.78,2024-01-15,us-east-1,720,i-1234567890abcdef0
S3,23.45,2024-01-15,us-east-1,500,my-s3-bucket
RDS,89.32,2024-01-15,us-west-2,720,database-prod-01
Lambda,12.67,2024-01-15,us-east-1,1000,my-lambda-function
CloudFront,34.56,2024-01-15,global,100,E1234567890123
ELB,45.23,2024-01-15,us-east-1,720,my-load-balancer
Route53,8.90,2024-01-15,global,1000,my-domain.com
```

#### Alternative AWS Headers (All Supported)
```csv
ProductName,BlendedCost,UsageStartDate,AvailabilityZone,UsageQuantity,InstanceId
Amazon Elastic Compute Cloud,156.78,2024-01-15T00:00:00Z,us-east-1a,720,i-1234567890abcdef0
Amazon Simple Storage Service,23.45,2024-01-15T00:00:00Z,us-east-1,500,my-s3-bucket
Amazon Relational Database Service,89.32,2024-01-15T00:00:00Z,us-west-2b,720,database-prod-01
```

### 🔷 **Azure Billing Files**

#### Standard CSV Format
```csv
Product/Service,Amount,BillingPeriod,Location,UsageQuantity,Resource
Virtual Machines,245.50,2024-01-15,East US,720,vm-webserver-01
Storage Accounts,15.30,2024-01-15,East US,1024,storageaccount123
Azure SQL Database,125.75,2024-01-15,West US 2,720,sqldb-production
App Service,67.20,2024-01-15,East US,720,webapp-frontend
Application Gateway,34.80,2024-01-15,East US,720,appgw-main
Azure Functions,8.45,2024-01-15,East US,500,func-processing
```

#### Alternative Azure Headers
```csv
ServiceName,TotalCost,Date,Region,Quantity,ResourceName
Compute,245.50,2024-01-15,East US,720,vm-webserver-01
Storage,15.30,2024-01-15,East US,1024,storageaccount123
Database,125.75,2024-01-15,West US 2,720,sqldb-production
```

### 🟡 **Google Cloud Billing Files**

#### Standard CSV Format
```csv
service.description,cost,usage_start_time,location.location,usage.amount,resource.name
Compute Engine,189.45,2024-01-15T00:00:00Z,us-central1,720,instance-web-server
Cloud Storage,28.90,2024-01-15T00:00:00Z,us-central1,2048,bucket-data-lake
Cloud SQL,156.20,2024-01-15T00:00:00Z,us-east1,720,sql-instance-prod
Cloud Functions,12.75,2024-01-15T00:00:00Z,us-central1,1000,function-processor
Cloud Load Balancing,45.60,2024-01-15T00:00:00Z,global,720,lb-frontend
Cloud CDN,23.40,2024-01-15T00:00:00Z,global,500,cdn-assets
```

### 📄 **JSON Format (Universal)**

Works with any cloud provider:

```json
[
  {
    "service": "EC2-Instance",
    "cost": 156.78,
    "date": "2024-01-15",
    "region": "us-east-1",
    "usage": 720,
    "resourceId": "i-1234567890abcdef0"
  },
  {
    "service": "S3",
    "cost": 23.45,
    "date": "2024-01-15",
    "region": "us-east-1",
    "usage": 500,
    "resourceId": "my-s3-bucket"
  },
  {
    "service": "RDS",
    "cost": 89.32,
    "date": "2024-01-15",
    "region": "us-west-2",
    "usage": 720,
    "resourceId": "database-prod-01"
  }
]
```

## 📥 How to Get Your Billing Files

### 🟠 **AWS - Cost and Usage Reports**

1. **Go to AWS Billing Console**
   - Navigate to [AWS Billing & Cost Management](https://console.aws.amazon.com/billing/)
   - Click on "Cost & usage reports"

2. **Create/Download Report**
   ```bash
   # Via AWS CLI (optional)
   aws ce get-cost-and-usage \
     --time-period Start=2024-01-01,End=2024-01-31 \
     --granularity DAILY \
     --metrics BlendedCost \
     --group-by Type=DIMENSION,Key=SERVICE
   ```

3. **Export from Cost Explorer**
   - Go to Cost Explorer → Reports
   - Select date range and filters
   - Click "Download CSV"

### 🔷 **Azure - Cost Management**

1. **Access Cost Management**
   - Go to [Azure Portal](https://portal.azure.com/)
   - Navigate to "Cost Management + Billing"

2. **Export Usage Data**
   - Click on "Cost analysis"
   - Set your filters and date range
   - Click "Export" → "Download to CSV"

3. **Automated Exports**
   ```bash
   # Via Azure CLI
   az costmanagement export create \
     --name "monthly-export" \
     --definition-type "Usage" \
     --dataset-granularity "Daily"
   ```

### 🟡 **Google Cloud - Billing Export**

1. **Enable Billing Export**
   - Go to [Cloud Console](https://console.cloud.google.com/)
   - Navigate to "Billing" → "Billing export"

2. **Export to CSV**
   - Go to "Reports" section
   - Select date range and services
   - Click "Export" → "CSV"

3. **BigQuery Export (Advanced)**
   ```sql
   -- Sample BigQuery query for billing data
   SELECT
     service.description as service,
     cost,
     usage_start_time as date,
     location.location as region,
     usage.amount as usage,
     resource.name as resourceId
   FROM `project.dataset.gcp_billing_export_v1_XXXXXX`
   WHERE _PARTITIONTIME >= "2024-01-01"
   ```

## 🎮 Demo Data Examples

### Complete AWS Demo File
Save as `aws-demo.csv`:
```csv
Service,Cost,Date,Region,Usage,ResourceId
EC2-Instance,156.78,2024-01-15,us-east-1,720,i-1234567890abcdef0
EC2-Instance,89.45,2024-01-16,us-west-2,720,i-0987654321fedcba0
S3,23.45,2024-01-15,us-east-1,500,my-s3-bucket
S3,18.90,2024-01-16,us-east-1,450,my-s3-bucket
RDS,89.32,2024-01-15,us-west-2,720,database-prod-01
RDS,92.15,2024-01-16,us-west-2,720,database-prod-01
Lambda,12.67,2024-01-15,us-east-1,1000,my-lambda-function
Lambda,15.20,2024-01-16,us-east-1,1200,my-lambda-function
CloudFront,34.56,2024-01-15,global,100,E1234567890123
ELB,45.23,2024-01-15,us-east-1,720,my-load-balancer
Route53,8.90,2024-01-15,global,1000,my-domain.com
```

### Complete Azure Demo File
Save as `azure-demo.csv`:
```csv
Product/Service,Amount,BillingPeriod,Location,UsageQuantity,Resource
Virtual Machines,245.50,2024-01-15,East US,720,vm-webserver-01
Virtual Machines,198.30,2024-01-16,West US 2,720,vm-api-server-01
Storage Accounts,15.30,2024-01-15,East US,1024,storageaccount123
Storage Accounts,18.75,2024-01-16,East US,1200,storageaccount123
Azure SQL Database,125.75,2024-01-15,West US 2,720,sqldb-production
Azure SQL Database,134.20,2024-01-16,West US 2,720,sqldb-production
App Service,67.20,2024-01-15,East US,720,webapp-frontend
Application Gateway,34.80,2024-01-15,East US,720,appgw-main
Azure Functions,8.45,2024-01-15,East US,500,func-processing
```

### Complete Google Cloud Demo File
Save as `gcp-demo.csv`:
```csv
service.description,cost,usage_start_time,location.location,usage.amount,resource.name
Compute Engine,189.45,2024-01-15T00:00:00Z,us-central1,720,instance-web-server
Compute Engine,167.80,2024-01-16T00:00:00Z,us-east1,720,instance-api-server
Cloud Storage,28.90,2024-01-15T00:00:00Z,us-central1,2048,bucket-data-lake
Cloud Storage,32.15,2024-01-16T00:00:00Z,us-central1,2300,bucket-data-lake
Cloud SQL,156.20,2024-01-15T00:00:00Z,us-east1,720,sql-instance-prod
Cloud SQL,162.45,2024-01-16T00:00:00Z,us-east1,720,sql-instance-prod
Cloud Functions,12.75,2024-01-15T00:00:00Z,us-central1,1000,function-processor
Cloud Load Balancing,45.60,2024-01-15T00:00:00Z,global,720,lb-frontend
Cloud CDN,23.40,2024-01-15T00:00:00Z,global,500,cdn-assets
```

## 🚀 Quick Start

### 1. **Try the Live Demo**
Visit [https://m3hr4nn.github.io/infra-cost-analyzer/](https://m3hr4nn.github.io/infra-cost-analyzer/) and click "🎮 Try Demo Data"

### 2. **Upload Your Own Data**
1. Export billing data from your cloud provider (see guides above)
2. Drag and drop the CSV/JSON file into the analyzer
3. Select your cloud provider or use auto-detect
4. View your cost analysis and optimization recommendations

### 3. **Local Development**
```bash
# Clone the repository
git clone https://github.com/m3hr4nn/infra-cost-analyzer.git
cd infra-cost-analyzer

# Open in browser
open index.html
# or use a local server
python -m http.server 8000
```

## 📊 What You'll Get

### **Cost Analysis Dashboard**
- 💰 **Total Cost** - Sum of all expenses
- 📅 **Daily Average** - Average spending per day
- 🔧 **Services Used** - Number of different services
- 🏆 **Top Service** - Highest cost service

### **Interactive Visualizations**
- 🍩 **Service Cost Distribution** - Donut chart showing cost breakdown
- 📈 **Trend Analysis** - Usage patterns over time
- 🌍 **Regional Spending** - Cost distribution by region

### **Smart Recommendations**
- 🎯 **Service Optimization** - Specific recommendations for your top services
- 🌐 **Multi-Region Consolidation** - Advice on reducing regional complexity
- ⏰ **Resource Scheduling** - Automated start/stop suggestions
- 💾 **Storage Optimization** - Lifecycle policies and tier recommendations
- 📊 **Cost Monitoring** - Budget and alert setup guidance

## 🔧 Technical Details

### **Architecture**
- **Frontend-Only** - No backend servers required
- **Client-Side Processing** - All analysis happens in your browser
- **Privacy-First** - Files are never uploaded or stored
- **GitHub Pages Compatible** - Static hosting ready

### **Libraries Used**
- **Chart.js** - Interactive data visualizations
- **PapaParse** - Robust CSV parsing
- **Vanilla JavaScript** - No heavy frameworks
- **Modern CSS** - Glassmorphism design with animations

### **Browser Compatibility**
- ✅ Chrome 90+
- ✅ Firefox 88+
- ✅ Safari 14+
- ✅ Edge 90+

## 🤝 Contributing

We welcome contributions! Here are some ways you can help:

### **Bug Reports & Feature Requests**
- Open an issue with detailed description
- Include sample data files (anonymized)
- Specify your browser and version

### **Development**
```bash
# Fork the repository
git clone https://github.com/yourusername/infra-cost-analyzer.git

# Make your changes
# Test with various file formats

# Submit a pull request
```

### **Adding New Cloud Providers**
1. Study the provider's billing file format
2. Add field mapping in the `performCostAnalysis()` function
3. Update the README with examples
4. Test with real data files

## 📝 Common File Issues & Solutions

### **File Not Recognized?**
- ✅ Ensure your CSV has headers in the first row
- ✅ Check that cost values are numbers (not text)
- ✅ Verify date format is YYYY-MM-DD or similar
- ✅ Remove any summary rows at the top/bottom

### **Missing Data?**
- ✅ Make sure cost column isn't empty
- ✅ Check for currency symbols ($, €, etc.) in cost fields
- ✅ Verify service names aren't blank

### **Provider Not Auto-Detected?**
- ✅ Manually select your cloud provider
- ✅ Check column names match expected formats
- ✅ Try renaming columns to standard names

## 📄 License

MIT License - feel free to use this project for personal or commercial purposes.

## 🌟 Star This Project

If you find this tool helpful, please ⭐ star the repository to help others discover it!

---

**Made with ❤️ for the cloud community**

*Helping developers optimize their cloud costs, one bill at a time.*
