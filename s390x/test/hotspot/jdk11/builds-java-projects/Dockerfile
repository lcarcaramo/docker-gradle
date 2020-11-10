FROM quay.io/ibmz/gradle:6.7

USER gradle

WORKDIR /home/gradle/project
COPY . .

RUN chown gradle *

CMD [ "gradle", "build", "-i" ]
