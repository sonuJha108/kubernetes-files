step1: create the docker file 
step2: create the image & tag that images
step3: push the docker image in docker hub
step4: create the namespace.yml deployment.yml service.yml file
step5: apply the all the files kubectl apply -f xyz
step6: last port forward | kubectl port-forward service/notes-app-service -n notes-app 8000:8000 --address=0.0.0.0
