FROM golang:1.17-alpine
RUN wget -O - https://raw.githubusercontent.com/cosmtrek/air/master/install.sh | sh -s -- -b $(go env GOPATH)/bin
WORKDIR /opt/app/
CMD ["air"]