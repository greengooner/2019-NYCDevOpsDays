## Kubernetes at Datadog: The Very Hard Way
Source Materials:
* Slides: [https://www.slideshare.net/RobertBoll/kubernetes-the-very-hard-way](https://www.slideshare.net/RobertBoll/kubernetes-the-very-hard-way)

Notes:
* A tale of early adoption
* In 2016:
    * Entirely in 1 AWS Region
    * EC2 instances with Chef and Capistrano
* Change of cloud providers required rebuild
* Scaling to thousands of nodes
* Toolbox Pattern
    * Deployed alongside workloads with images that have tools for ops
* Native Pod Routing
    * Overlay networks are expensive (encap VXLAN,IPIP,etc and bridging from host to container)
    * CNI plugins configure networking; datadog uses IPVLAN plugin
    * Put pods on the native network for performance and simplicity
* Container Runtime
    * Containerd offers a simpler alternative to docker (smaller codebase, less real world use)
    * Some bad bugs (Zombie process causing hung shim (still has some issues with this, they monitor for it), maintainers are very responsive)
    * containerd - Less surface area but less mature
* Control Plane Topo
    * Scale indepently by seperating components (Datastore (etcd), API Server, Scheduler, Controller Manager) onto seperate hosts for large clusters.
    * apiserver is particularly memory intensive in large clusters
* What's broken?
    * Load Balancer Svcs
        * kube-proxy on each host forward traffic to right pod; Every host is on every load balancer
        * ExternalTraficPolicy will cause failed traffic path if there is no pod with the service
        * Pod Native Ingress - means that traffic is sent directly to pods
            * Require routable pod IP and provider abstraction
        * No support for TCP
            * Datadog may build this since it doesnt exist now
    * PKI
        * Used everywhere
        * No proper support for rotating credentials
        * WNo real solutions
    * Ecosystem
        * Dyanmic community but many componeents not tested at scale and lack prod usage
        * Ex. Autoscaler, State-Metrics, External-DNS
        * Carefully vet your dependencies
* Surprises
    * Cargo Culting
        * Invest in Training!
            * The tech is new for everyone!
            * Engineers will find a way, wont be pretty
    * Namespace Orgs
        * Namespace isolates workloads; DO NOT use a single namespace
        * Pefromance degredations in etcd with large namespaces
        * Rought guideline: ~3k nodes per namespace
    * Avoid Pod Admission Web Hooks
    * Avoid Image Policy Always
* Lessons Learned
    * Paying early adopter tax
        * It's expensive
    * Communicate with your customers
        * Communicate clearly
        * Share success, challenges, and plans
* Incidents as an early adopter
    * Two fundamental approaches
        * Restore service immediately, debug with forensics
        * Investingate causes in real time
            * Can extend disruption so not always available

