FROM quay.io/ibmz/gradle:6.7

WORKDIR /home/gradle/project
COPY . .

RUN chown gradle *

USER gradle

CMD [ "gradle", "build", "-i" ]
