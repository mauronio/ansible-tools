# Ansible OCI runtime Image

## Build for Oracle Linux 7, Ansible 2.9, Python 2.7

docker build . -f Dockerfile-ans29py27 -t ansible-oci-runtime:ans29py27 --no-cache

## Distribution

docker tag localhost/ansible-oci-runtime:(tag) (registry URL)/(username)/ansible-oci-runtime:(tag)
docker login (registry URL) -u '(username)' --password '(password)'
docker push (registry url)/(username)/ansible-oci-runtime:(tag)

Examples:
  docker tag localhost/ansible-oci-runtime:ans29py27 quay.io/mauriciogomez/ansible-oci-runtime:ans29py27
  docker login quay.io
  docker push quay.io/mauriciogomez/ansible-oci-runtime:ans29py27

## Usage

docker pull (registry URL)/(username)/ansible-oci-runtime:(tag)
docker run -e USER=ansible -e MY_UID=(local user UID) -e MY_GID=(local user group UID) -v ~/.ssh:/root/.ssh -v ~/.oci:/root/.oci -v .:/workspace -w "/workspace" ansible-oci-runtime:(tag) ansible-playbook playbook.yaml

Examples:
  docker pull quay.io/mauriciogomez/ansible-oci-runtime:ans29py27
  docker run -e USER=ansible -e MY_UID=54322 -e MY_GID=54322 -v ~:/home/opc -v ~/.ssh:/root/.ssh -v ~/.oci:/root/.oci -v /home/mgomez:/home/mgomez  -v .:/workspace -w "/workspace" ansible-oci-runtime:ans29py27 ansible-playbook playbook.yaml

