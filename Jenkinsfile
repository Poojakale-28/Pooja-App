

pipeline {
		agent {
			
			label {
					label "built-in"
					customWorkspace "/mnt/MyWorkspace"
			}
		
		}
		
		stages {
			stage ("one") {
				steps {
					sh "sudo docker ps -aq | xargs -r sudo docker rm -f"
					sh "sudo docker run -itdp 80:80 --name Cont1 httpd"
					sh "sudo chmod -R 777 /mnt/MyWorkspace/index.html"
					sh "docker cp /mnt/MyWorkspace/index.html Cont1:/usr/local/apache2/htdocs"
				}
			}
			
		}
}
