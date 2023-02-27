### Draining 
kubectl drain "nom du node "

le draining se fait lors d'une maintenance du cluster quand on veut par example mettre en pause un node et migrer des pods sur un autre node 

parfois on a besoin du flag ignore daemonset pour pouvoir enchainer a une 

une fois la maintenance et terminé on lance le la commande 

Kubectl uncoron "nom du node "

### upgrading 

1. le draining du node qu'on veut mettre a jour 
2. on met a jour le node avec :  apt-mark unhold kubeadm && \
 apt-get update && apt-get install -y kubeadm=1.26.x-00 && \
 apt-mark hold kubeadm
3. et puis on lance la commande kubeadm upgrade plan pour voir les changement qui vont se passer et puis enfin pour appliquer les changement on lance kubeadm upgrade apply 

4. pour les autres nodes on utilise les memes etapes et au lieu de lancer upgrade plan on lance sudo kubeadm upgrade node puis apply 






