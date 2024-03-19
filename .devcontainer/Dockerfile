FROM node:20-bullseye-slim AS node

FROM mcr.microsoft.com/devcontainers/base:bullseye

# Node.jsのイメージからDevContainerのbaseイメージにNode.jsをコピーする
# TODO: DevContainerのFeaturesでNode.jsをインストールしたいがコンテナービルドエラーを解決できなかった
COPY --from=node /usr/local/bin/node /usr/local/bin/node
COPY --from=node /usr/local/lib/node_modules /usr/local/lib/node_modules
RUN ln -s /usr/local/bin/node /usr/local/bin/nodejs \
    && ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npm \
    && ln -s /usr/local/lib/node_modules/npm/bin/npm-cli.js /usr/local/bin/npx

RUN npm install -g @microsoft/inshellisense
