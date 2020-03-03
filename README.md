# oc-secretes
 
    1) oc new-project myproject
    2)  oc new-app --name=app1 --docker-image=mysql:5.6 --env MYSQL_ROOT_PASSWORD=redhat
    3)  oc get pods -w
    4)  oc get dc
    5)  oc edit dc app1
    6)  oc create secret generic mysecrete --from-literal=mypass=redhat;
    7)  oc get secret
    8)   oc edit deployment mysql
    9)  oc edit dc app1 
    10)  oc describe secret mysecrete
    
    IN  oc edit dc app1  ::
         name: MYSQL_ROOT_PASSWORD
         valueFrom:
            secretKeyRef:
              key: mypass
              name: mysecrete
