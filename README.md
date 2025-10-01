# Bài tập Python — Repo DTH235628

Tổng quan
- Repo chứa bài tập Python theo chương dưới dạng script (.py) và notebook (.ipynb).
- Thư mục chính:
  - `Bai Tap Giao Trinh/` — script theo giáo trình 
  - `Bai Tap Moodle/` — notebook tổng hợp theo chương.
  - `.venv/` — môi trường ảo (không nên push).

Yêu cầu
- Python 3.9+ (khuyến nghị 3.13).
- pip, venv. Dùng ipykernel để chạy notebook trong VS Code / Jupyter.

Thiết lập nhanh (Linux / zsh)
```bash
# tạo và kích hoạt venv
python3 -m venv .venv
. ./.venv/bin/activate

# cài phụ thuộc (nếu có)
pip install -r requirements.txt

# (tuỳ chọn) cài ipykernel để notebook nhận kernel của venv
pip install ipykernel
python -m ipykernel install --user --name DTH235628_py --display-name "Python (DTH235628)"
```

Chạy script (.py)
```bash
# kích hoạt venv
. ./.venv/bin/activate

# chạy script ví dụ
./.venv/bin/python "Bai Tap Giao Trinh/Chuong 1/bt10.py"
```
Lưu ý: nhiều script dùng input() — chạy trong terminal và nhập khi được yêu cầu.

Mở và chạy notebook (.ipynb)
- Mở bằng VS Code hoặc Jupyter Lab/Notebook.
- Chọn kernel `DTH235628_py` / "Python (DTH235628)".
- Chạy từng ô (Shift+Enter). Tránh “Run All” nếu có input().

Tạo `requirements.txt`
```bash
. ./.venv/bin/activate
pip freeze > requirements.txt
```

Không push môi trường ảo
- Thêm `.venv/` vào `.gitignore`.
- Commit `requirements.txt` thay vì push `.venv/`.

Chạy notebook không tương tác
- Thay input() bằng giá trị mẫu hoặc dùng:
```bash
pip install nbconvert
jupyter nbconvert --to notebook --execute "Bai Tap Moodle/Bai Tap Chuong 4/baitapchuong4.ipynb" --output executed.ipynb
```

Khắc phục nhanh
- Kernel không hiện: kiểm tra `jupyter kernelspec list`, reload VS Code.
- Thiếu pip trên Python hệ thống: dùng venv hoặc cài pip cho interpreter đó.

Nếu cần hỗ trợ tạo `requirements.txt`, cập nhật `.gitignore` hoặc tạo bản notebook demo không tương tác, cho biết hành động mong muốn.
