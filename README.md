# workstation
A docker compose for email, browsing and development


    docker exec -i workstation_thunderbird_1 /bin/bash -c 'cat >> /home/user/.ssh/authorized_keys' < ~/.ssh/id_rsa.pub


Connect to xpra

    xpra --ssh="ssh -o \"StrictHostKeyChecking no\" -p 2020" attach ssh:user@localhost:100

Start an application

    ssh -p 2020 user@localhost DISPLAY=:100 thunderbird

    

Make backup
    
    docker run --volumes-from workstation_userdata_1 -v $(pwd):/backup ubuntu tar cvf /backup/backup.tar /home/user
