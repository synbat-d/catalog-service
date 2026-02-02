# Build
custom_build(
    # Name of the container image
    ref = 'catalog-service',  # <--- ВОТ ЗДЕСЬ БЫЛА ОШИБКА (нужна запятая)

    # Command to build the container image
    command = 'gradlew.bat bootBuildImage --imageName %EXPECTED_REF%',

    # Files to watch that trigger a new build
    deps = ['build.gradle', 'src']
)

# Deploy
# Исправил опечатку: функция называется k8s_yaml, а не k8s_yml
k8s_yaml(['k8s/deployment.yml', 'k8s/service.yml'])

# Manage
k8s_resource('catalog-service', port_forwards = ['9001'])