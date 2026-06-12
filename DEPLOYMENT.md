# Deployment Information

## Public URL
https://day12-2a202600672-nguyenvonguyenhuy-ha.onrender.com

## Platform
Render

## Test Commands

### Health Check
```bash
curl https://day12-2a202600672-nguyenvonguyenhuy-ha.onrender.com/health
# Expected output: {"status": "ok", ...}
```

### Readiness Check
```bash
curl https://day12-2a202600672-nguyenvonguyenhuy-ha.onrender.com/ready
# Expected output: {"ready": true}
```

### API Test (without authentication)
```bash
curl -X POST https://day12-2a202600672-nguyenvonguyenhuy-ha.onrender.com/ask \
  -H "Content-Type: application/json" \
  -d '{"question": "Hello"}'
# Expected output: {"detail": "Invalid or missing API key. Include header: X-API-Key: <key>"} (HTTP 401)
```

### API Test (with authentication)
```bash
curl -X POST https://day12-2a202600672-nguyenvonguyenhuy-ha.onrender.com/ask \
  -H "X-API-Key: <your-agent-api-key>" \
  -H "Content-Type: application/json" \
  -d '{"question": "Hello"}'
# Expected output: {"question": "Hello", "answer": "...", "model": "...", "timestamp": "..."} (HTTP 200)
```

## Environment Variables Set
- `PORT`: 8000 *(Do Railway/Render gán tự động)*
- `AGENT_API_KEY`: `your-secret-api-key` *(Khóa API dùng để xác thực)*
- `ENVIRONMENT`: `production` *(Môi trường chạy)*
- `REDIS_URL`: `redis://redis-service-host:6379/0` *(Nếu dùng Redis trên cloud)*
- `LOG_LEVEL`: `INFO` *(Mức độ logging)*

## Screenshots
- **Deployment dashboard:** [screenshots/dashboard.png](screenshots/dashboard.png)
- **Service running:** [screenshots/running.png](screenshots/running.png)
- **Test results:** [screenshots/test.png](screenshots/test.png)
