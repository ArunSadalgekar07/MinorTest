# GPU Monitoring & User Management Dashboard

A Flask-based web dashboard for monitoring GPU and CPU stats, managing users, and analyzing GPU usage from CSV files.

---

## 🚀 Features

- **Live GPU & CPU Monitoring** (Linux)
- **User Management** (create, delete, list, search, inactive users)
- **CSV Analysis**: Upload and visualize GPU usage data
- **Downloadable Reports** (charts, inactive users)
- **Modern, Responsive UI** with loading indicators and interactive charts

---

## Screenshots
![IMG-20251219-WA0035 1](https://github.com/user-attachments/assets/2acd16a7-7d3e-4bb0-9302-189d814229a8)
![IMG-20251219-WA0046 1](https://github.com/user-attachments/assets/6cfa3780-2af1-446b-b17c-7123fea4eb0a)
![IMG-20251219-WA0044 1](https://github.com/user-attachments/assets/53493072-bf0a-4a91-9a50-5aa579d3a2ab)
![IMG-20251219-WA0042 1](https://github.com/user-attachments/assets/eb04cc3b-1b37-403d-8881-ecf2696d84ae)
![IMG-20251219-WA0045 1](https://github.com/user-attachments/assets/04367d10-70d7-4e26-847c-c60ebf830c83)
![IMG-20251219-WA0049 1](https://github.com/user-attachments/assets/349a0ac3-3e6b-45c6-ae1d-0c3a2ad340f4)
![IMG-20251219-WA0043 1](https://github.com/user-attachments/assets/4fbbe908-02c8-4ed9-a512-c450b652e2f0)
![IMG-20251219-WA0050 1](https://github.com/user-attachments/assets/dd1d3a61-f932-4586-b9ce-1a3a9a186271)
![IMG-20251219-WA0052 1](https://github.com/user-attachments/assets/f178056a-34d7-4f73-a3fe-e453a1701cdd)
![IMG-20251219-WA0053 1](https://github.com/user-attachments/assets/4c6cd68d-dcf5-4f48-88cd-e9ac460159c8)

## 🛠️ Setup Instructions

### 1. **Clone the Repository**
```bash
git clone <your-repo-url>
cd <your-repo-directory>
```

### 2. **Install Dependencies**
```bash
pip install -r requirements.txt
```

### 3. **Run the App**
```bash
python app.py
```
- The app will be available at [http://localhost:5000](http://localhost:5000)

### 4. **Login**
- Default credentials:  
  **Username:** `admin`  
  **Password:** `admin`

---

## 📂 Folder Structure

```
.
├── app.py
├── requirements.txt
├── utils/
│   └── shell_ops.py
├── static/
│   └── ... (CSS, images)
├── templates/
│   └── ... (HTML files)
```



## 🧑‍💻 Usage Examples

- **Monitor live GPU/CPU stats** on the dashboard.
- **Upload a CSV** on the CSV Analysis page to visualize GPU usage.
- **Manage users** (create, delete, list, search, view inactive).
- **Download** charts and inactive user lists as files.

---

## 📝 API Documentation

### **Authentication**
- Most API endpoints require a valid session (login via web UI).

---

### **Endpoints**

#### `GET /api/gpu_stats`
- **Description:** Get live GPU stats.
- **Auth:** Session required.
- **Response:**  
  ```json
  [
    {
      "index": 0,
      "name": "NVIDIA RTX 6000 Ada Generation",
      "gpu_util": 2,
      "mem_util": 413,
      "mem_total": 49140,
      "mem_used": 413,
      "mem_free": 48727,
      "temperature": 45
    },
    ...
  ]
  ```

#### `GET /api/cpu_live_info`
- **Description:** Get live CPU info (Linux only).
- **Auth:** None (or session, depending on your setup).
- **Response:**  
  ```json
  {
    "cpu_percent": 12.5,
    "per_core": [10.0, 15.0, ...],
    "load_avg": [0.5, 0.7, 0.8],
    "model_name": "Intel(R) Xeon(R) CPU"
  }
  ```

#### `POST /api/analyze_csv`
- **Description:** Analyze uploaded GPU CSV file.
- **Body:** `multipart/form-data` with `csvFile`
- **Response:**  
  ```json
  [
    {
      "index": 0,
      "name": "NVIDIA RTX 6000 Ada Generation",
      "timestamps": ["2025-04-29 14:18:23", ...],
      "utilization": [2, ...],
      "memory": [413, ...]
    },
    ...
  ]
  ```

---

## 🔒 Security Notes

- Change the default admin password after setup.
- For production, use HTTPS and secure session management.

---

## 🧩 Contributing

Pull requests and suggestions are welcome!


