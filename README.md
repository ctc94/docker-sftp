
// docker stand-alone 실행
// ssh키로 접속할 수 있게 실행

docker run \\
    -v "$PWD/ssh_host_rsa_key.pub:/home/foo/.ssh/keys/ssh_host_rsa_key.pub:ro" \\
        -v "$PWD/upload:/home/foo/share" \\
	    -p 2222:22 -d atmoz/sftp \\
	        foo::
		
		//공개/비공개 키 만들기
		ssh-keygen -t rsa -b 4096 -f ssh_host_rsa_key < /dev/null# docker-sftp
