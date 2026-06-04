# Build
custom_build(
    ref = 'catalog-service',
    command = 'cmd /c gradlew.bat bootJar -x test && docker build -t %EXPECTED_REF% .',
    deps = ['build.gradle', 'src']
)

# Deploy
k8s_yaml(kustomize('k8s'))

# Manage
k8s_resource('catalog-service', port_forwards=['9001'])