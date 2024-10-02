# Python 3.9 베이스 이미지 사용
FROM python:3.9-slim

# 작업 디렉터리 생성
RUN mkdir /backend
RUN mkdir /ml

# 종속성 파일을 컨테이너에 복사
COPY ./backend/requirements.txt /backend/requirements.txt

# 종속성 설치
RUN pip install -r backend/requirements.txt

# 애플리케이션 코드를 컨테이너에 복사
COPY ./backend /backend
COPY ./ml /ml

# 해당 포트를 외부로 개방
EXPOSE 8000

# Uvicorn 서버 실행
CMD ["uvicorn", "backend.main:app", "--host", "0.0.0.0", "--port", "8000"]


