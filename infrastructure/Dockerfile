FROM golang:alpine

ENV APP_NAME graph-playground
ENV REPO_BASE_URL github.com/decebal
ENV APP_PATH $GOPATH/src/$REPO_BASE_URL/$APP_NAME/infrastructure

COPY . $APP_PATH
WORKDIR $APP_PATH
RUN apk add --update rsync && \
    rsync -a $APP_PATH/vendor/* $GOPATH/src/

CMD ["sh", "-c", "go run $(echo ${APP_PATH}/src/app.go)"]
