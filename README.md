# Voter Anomaly Detection System

A comprehensive system designed to detect potential voting fraud and anomalies in election data using blockchain technology and advanced anomaly detection algorithms.

## 🎯 Overview

This system combines blockchain-based vote recording with real-time anomaly detection to ensure election integrity. It monitors voting patterns, detects suspicious activities, and provides alerts for potential fraud scenarios.

## ✨ Features

- **Blockchain Integration**: Secure vote recording using blockchain technology with proof-of-work consensus
- **Real-time Anomaly Detection**: Monitors for various types of voting anomalies:
  - Votes exceeding registered voter count
  - Sudden spikes in voting activity
  - Zero vote scenarios
  - Unusual voting patterns
- **Database Management**: SQLite database for storing voter and vote data
- **Alert System**: Email notifications for detected anomalies
- **Comprehensive Testing**: Built-in test cases for anomaly detection scenarios

## 🏗️ Project Structure

```
Voter-Anomaly-Detection-System/
├── main.py                 # Main application entry point
├── detect_anomalies.py     # Anomaly detection algorithms
├── setup_database.py       # Database setup and initialization
├── alert_system.py         # Email alert functionality
├── blockchain.py           # Blockchain implementation
├── voting_system.db        # SQLite database
├── fraud_alerts.log        # Log file for detected anomalies
├── static/                 # Static assets
│   ├── cute.png
│   └── fortnite.png
└── Election Software Integrity Tool.pptx  # Documentation
```

## 🚀 Installation & Setup

### Prerequisites

- Python 3.7 or higher
- Required Python packages (install via pip):
  ```bash
  pip install pandas sqlite3
  ```

### Quick Start

1. **Clone or download the project files**

2. **Set up the database**:
   ```bash
   python setup_database.py
   ```

3. **Run the main application**:
   ```bash
   python main.py
   ```

## 📊 How It Works

### 1. Database Setup
The system creates two main tables:
- **voters**: Stores voter registration information
- **votes**: Records individual votes with timestamps and locations

### 2. Anomaly Detection
The system monitors for several types of anomalies:
- **Vote Count Anomalies**: Detects when votes exceed registered voters
- **Voting Pattern Anomalies**: Identifies sudden spikes or unusual patterns
- **Zero Vote Scenarios**: Flags precincts with no voting activity

### 3. Blockchain Integration
- Each vote is recorded as a transaction in a blockchain
- Proof-of-work consensus ensures data integrity
- Immutable audit trail for all voting activities

### 4. Alert System
- Email notifications for detected anomalies
- Configurable alert thresholds
- Detailed logging of all detected issues

## 🔧 Configuration

### Email Alerts
To enable email alerts, set up environment variables:
```bash
export EMAIL_PASSWORD="your_email_password"
```

Update `alert_system.py` with your email credentials:
```python
sender_email = "your_email@gmail.com"
receiver_email = "admin_email@gmail.com"
```

### Anomaly Thresholds
Modify detection thresholds in `detect_anomalies.py`:
```python
# Adjust spike detection threshold
if votes - previous_votes > 50:  # Change 50 to your preferred threshold
```

## 🧪 Testing

The system includes built-in test cases that simulate various voting scenarios:

1. **Normal Voting**: Standard voting patterns
2. **Fraud Detection**: Votes exceeding registered voters
3. **Spike Detection**: Sudden increases in voting activity
4. **Zero Vote Scenarios**: Precincts with no voting activity

Run tests by executing:
```bash
python main.py
```

## 📈 Usage Examples

### Running Anomaly Detection
```python
from detect_anomalies import check_all_anomalies

# Check for anomalies in the database
result = check_all_anomalies("voting_system.db")
print(result)
```

### Manual Anomaly Testing
```python
from detect_anomalies import check_manual_anomalies

# Test specific voting scenarios
anomalies = check_manual_anomalies(votes=120, registered_voters=100, previous_votes=80)
```

### Blockchain Operations
```python
from main import Blockchain, Block

# Create and add a new block
blockchain = Blockchain()
new_block = Block(index=1, transactions={'voter_id': 1, 'candidate_id': 101}, previous_hash=blockchain.chain[-1].hash)
proof = blockchain.proof_of_work(new_block)
blockchain.add_block(new_block, proof)
```

## 🔍 Monitoring & Logs

- **fraud_alerts.log**: Contains detailed logs of all detected anomalies
- **Console Output**: Real-time feedback during system operation
- **Database Logs**: SQLite database maintains transaction history

## 🛡️ Security Features

- **Blockchain Immutability**: Once recorded, vote data cannot be altered
- **Hash Verification**: Cryptographic verification of data integrity
- **Audit Trail**: Complete history of all voting activities
- **Secure Database**: SQLite with foreign key constraints

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## 📝 License

This project is designed for educational and research purposes in election security and fraud detection.

## ⚠️ Disclaimer

This system is intended for educational and research purposes. For production use in actual elections, additional security measures, compliance checks, and regulatory approvals may be required.

## 📞 Support

For questions or issues, please review the code comments and documentation included in the project files.

---

**Note**: This system demonstrates advanced concepts in election security, blockchain technology, and anomaly detection. It serves as a foundation for understanding how modern voting systems can be secured against fraud and manipulation. 