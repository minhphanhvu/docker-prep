FROM node:14

EXPOSE 5000

RUN groupadd mygroup

RUN useradd -ms /bin/bash -G mygroup appuser

USER appuser

WORKDIR /usr/src/app

RUN chown -R appuser:mygroup /usr/src/app

COPY . .

RUN npm install

RUN REACT_APP_BACKEND_URL=http://localhost:8080 npm run build

RUN npm install -g serve

CMD serve -s -l 5000 build