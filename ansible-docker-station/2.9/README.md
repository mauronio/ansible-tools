# Registry Login

docker login quay.io -u 'mauriciogomez' --password '(password)'

# Build

docker build . -t mauriciogomez/ansible-tools:2.9 
docker run mauriciogomez/ansible-tools:2.9
docker tag mauriciogomez/ansible-tools:2.9 (registry url)/mauriciogomez/ansible-tools:2.9
docker push (registry url)/mauriciogomez/ansible-tools:2.9
