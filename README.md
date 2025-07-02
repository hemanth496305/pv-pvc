# pv-pvc
persistent volume and persistent volume claim

while working with "minikube"
step1: work with two screens running same machine (1-minikube and 2-vm)
step2: login into minikube cluster "minikube ssh"
step3: create a directory "/mnt/data"
step4: create a "index.html" file or clone the code here 
      note: git is not available in cluster, we must install git first "sudo apt update -y && apt install git -y"
            sudo git clone <url> /mnt/data
            check " ls /mnt/data/
step5: create persistent volume yaml file "pv.yaml"
        -> kubectl apply -f pv.yaml
step6: create persistent volume claim "pvc.yaml"
        -> kubectl apply -f pvc.yaml
step7: create pod (attach volume) "pod.yaml"
        -> kubectl apply -f pod.yaml
      note: if we did not mention lable in pod use " kubectl label pod <pod-name> app=<label-name>
step8: create a service file "service.yaml"
        -> kubectl apply -f service.yaml
step9: to access the application form external source use
        " kubectl  port-forward --address 0.0.0.0 service/<service-name> 30001:80
step10: check in browser with "publicip:30001"
  
        
