# coding-project-template# cloud
# cloud

웹 페이지를 호스팅하려면 터미널에서 다음 명령어를 실행하세요.
1
python3 -m http.server

Dockerfile에서 이미지를 빌드하기
2
docker build -t guess-the-capital .

이미지를 실행합니다.
3
docker run -it -d -p 8080:80 guess-the-capital

Project Build
4
docker build . -t us.icr.io/${SN_ICR_NAMESPACE}/guess-the-capital

이미지를 IBM Cloud에 푸시하기
5
docker push us.icr.io/${SN_ICR_NAMESPACE}/guess-the-capital

IBM CE에 이미지를 배포합니다.
6
ibmcloud ce application create --name guess-the-capital --image us.icr.io/${SN_ICR_NAMESPACE}/guess-the-capital --registry-secret icr-secret --port 80


(옵션)
ibmcloud ce application get --name guess-the-capital

==========================================================


위의 경우는 ibm cloud ide를 사용한
예시이므로 이미지 빌드 이미지 푸시 배포시 Cloud Guide를 준수하면 됨^^
