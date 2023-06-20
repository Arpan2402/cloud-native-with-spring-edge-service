# Build
custom_build(
    # Name of the container image
    ref = 'edge-service',
    # Command to build the container image
    command = 'mvn spring-boot:build-image -D skipTests -D spring-boot.build-image.imageName=%EXPECTED_REF%',
    # Files to watch that trigger a new build
    deps = ['pom.xml', 'src']
)

# Deploy
k8s_yaml(['deploy/k8s/application/deployment.yml', 'deploy/k8s/application/service.yml'])

# Manage
k8s_resource('edge-service', port_forwards=['9000'])