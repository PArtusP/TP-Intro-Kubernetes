TP-INTRO-Kurbenetes
1.premierement on install kind avec les commande suivante:
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.12.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind

.pour installer kubectl:
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x kubectl
sudo mv kubectl /usr/local/bin/

2.A tout d'abord on créer un fichier .yaml (ici "nginx-pod.yaml") pour configurer le déploiment
-on créé un cluster kubernetes avec kind:
"kind create cluster"
puis on fait "kubectl apply -f nginx-pod.yaml" pour créer notre pod

2.B pour voirs nos pods sur le port 80 il suffit d'utiliser la commande:
"kubectl get pods"
ici j'ai error: unable to forward port because pod is not running. Current status=Pending comme erreur il faut attendre que le pod se lance

une fois notre pod "ready" on peut visiter la page du port 8080 avec "kubectl port-forward nginx-pod 8080:80"


