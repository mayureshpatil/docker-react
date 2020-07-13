node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', '79f32187-a82b-4e99-bde5-b146a10c4501') {

        def customImage = docker.build("miltonc/dockerwebapp")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
