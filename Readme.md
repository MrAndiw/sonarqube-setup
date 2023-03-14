[![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)

## How to setup Sonarqube

Setup

    1. docker volume create sonarqube-data-volume
    2. docker network create sonarqube-network
    3. docker run -v sonarqube-data-volume:/opt/sonarqube/data --network sonarqube-network --name sonarqube-server -p 9000:9000 -d sonarqube:9.9-community

Run Sonar Scanner

    4. docker run --network sonarqube-network \
    --rm \
    -e SONAR_HOST_URL="http://sonarqube-server:9000" \
    -e SONAR_LOGIN="sqp_66fc6bbefca24cbfbadc79ce1f0635365c4fea49" \
    -v "$(pwd):/usr/src" \
    sonarsource/sonar-scanner-cli
