    @Library(Jenkins_shared_lib) _

    properties([
        parameters([
            string(name: 'image_tag'),
            choice(name: 'deploy_to', choices: ['dev', 'test', 'prod'], description: 'Environment')
        ])
    ])


    def configMap = [
        GITHUB_REPO: "catalogue",
        image_tag: (params.image_tag),
        deploy_to: (params.deploy_to)
    ]


    nodejsDeploy(configMap)