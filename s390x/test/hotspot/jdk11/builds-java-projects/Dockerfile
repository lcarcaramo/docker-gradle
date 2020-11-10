FROM quay.io/ibmz/gradle:6.7

USER gradle

WORKDIR /home/gradle/project
COPY . .

CMD [ "gradle", "build", "-i" ]
