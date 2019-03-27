FROM rust:1.33

RUN apt-get update \
    && apt-get install -y `apt-cache depends firefox-esr | awk '/Depends:/{print$2}'` \
    && cargo install wasm-pack \
    && rustup target add wasm32-unknown-unknown \
    && cd /tmp \
    && wget https://ftp.mozilla.org/pub/firefox/releases/66.0/linux-x86_64/en-GB/firefox-66.0.tar.bz2 \
    && tar -xvjf firefox-66.0.tar.bz2 \
    && cp -R firefox /usr/lib/firefox \
    && ln -s /usr/lib/firefox/firefox /usr/bin/firefox