FROM python:3.8-slim as basement
COPY requirements.txt requirements.txt
RUN pip3 install --user -r requirements.txt

FROM python:3.8-slim
COPY --from=basement /root/.local /root/.local
COPY . .
ENV PATH=/root/.local/bin:$PATH
CMD [ "python", "manage.py", "runserver" ]
