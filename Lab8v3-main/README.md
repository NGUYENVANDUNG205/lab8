
# Lab 8 v3 - LLM Reasoning & Context-aware Decision for AIoT

## Chạy nhanh

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS/Linux
source .venv/bin/activate
pip install -r requirements.txt
python run_lab8_demo.py
uvicorn app:app --reload --host 0.0.0.0 --port 8000
```

Mở trình duyệt: http://127.0.0.1:8000/
<img width="1918" height="967" alt="image" src="https://github.com/user-attachments/assets/3635cf3c-22d8-4129-9148-6f3c6fe567cf" />


## Ý tưởng chính

Dashboard có ba tầng so sánh:
<img width="1562" height="307" alt="image" src="https://github.com/user-attachments/assets/fa5bd28e-cf50-4575-9368-5eab81d539c0" />

1. Sensor only: chỉ cảm biến và rule cứng.
2. Sensor + AI models: thêm evidence từ Lab 3 anomaly, Lab 4 forecasting, Lab 6 motion/camera, Lab 7 vision.
3. Sensor + AI models + LLM: LLM tổng hợp context, giải thích, trả JSON decision, sau đó safety gate kiểm tra.

## Chế độ chạy LLM

- `mock`: luôn chạy được, không cần Internet/API key/Ollama.
- `local`: gọi Ollama tại `http://localhost:11434`, ví dụ model `qwen3:1.7b`.
- `api`: placeholder/fallback để giảng viên gắn API cloud nếu muốn.
<img width="1897" height="930" alt="image" src="https://github.com/user-attachments/assets/37042918-db8f-461a-9cfa-19640fe82b17" />
<img width="1915" height="960" alt="image" src="https://github.com/user-attachments/assets/e1d90a89-7a57-4e1e-8b1a-a49a25a62459" />

