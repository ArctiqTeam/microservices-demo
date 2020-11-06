trigger_mode(TRIGGER_MODE_MANUAL)

settings = read_json('tilt_option.json', default={})
default_registry(settings.get('default_registry', ''))

# Deploy: tell Tilt what YAML to deploy
k8s_yaml('kubernetes-manifests/adservice.yaml')
k8s_yaml('kubernetes-manifests/cartservice.yaml')
k8s_yaml('kubernetes-manifests/checkoutservice.yaml')
k8s_yaml('kubernetes-manifests/currencyservice.yaml')
k8s_yaml('kubernetes-manifests/emailservice.yaml')
k8s_yaml('kubernetes-manifests/frontend.yaml')
k8s_yaml('kubernetes-manifests/loadgenerator.yaml')
k8s_yaml('kubernetes-manifests/paymentservice.yaml')
k8s_yaml('kubernetes-manifests/productcatalogservice.yaml')
k8s_yaml('kubernetes-manifests/recommendationservice.yaml')
k8s_yaml('kubernetes-manifests/shippingservice.yaml')
k8s_yaml('kubernetes-manifests/redis.yaml')

# Build: tell Tilt what images to build from which directories
docker_build('adservice', 'src/adservice')
docker_build('cartservice', 'src/cartservice')
docker_build('checkoutservice', 'src/checkoutservice')
docker_build('currencyservice', 'src/currencyservice')
docker_build('emailservice', 'src/emailservice')
docker_build('frontend', 'src/frontend')
docker_build('loadgenerator', 'src/loadgenerator')
docker_build('paymentservice', 'src/paymentservice')
docker_build('productcatalogservice', 'src/productcatalogservice')
docker_build('recommendationservice', 'src/recommendationservice')
docker_build('shippingservice', 'src/shippingservice')

# Watch: tell Tilt how to connect locally (optional)
k8s_resource('frontend', port_forwards=8100)

allow_k8s_contexts('gke_controlstation1-215819_northamerica-northeast1_prd1')
