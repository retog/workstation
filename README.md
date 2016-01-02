# workstation
A docker compose for email, browsing and development


    docker exec -i workstation_thunderbird_1 /bin/bash -c 'cat >> /home/user/.ssh/authorized_keys' < ~/.ssh/id_rsa.pub


Connect to xpra for communication tools

    xpra --ssh="ssh -o \"StrictHostKeyChecking no\" -p 2020" attach ssh:user@localhost:100

For dev tools

    xpra --ssh="ssh -o \"StrictHostKeyChecking no\" -p 2222" attach ssh:user@localhost:100

Start an application

    ssh -p 2020 user@localhost DISPLAY=:100 thunderbird

or

    ssh -p 2222 user@localhost DISPLAY=:100 start-dev-tools.sh
    

Make backup
    
    docker run --volumes-from workstation_userdata_1 -v $(pwd):/backup ubuntu tar cvf /backup/backup.tar /home/user
