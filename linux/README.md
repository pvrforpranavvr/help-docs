### COMMONLY USED LINIX COMMANDS

##### Change Directory
    cd <DIR_NAME>
##### Go to root dir
    cd
or

    cd.
##### Go back to previous directory
    cd ..
##### Copy files
    cp <SOURCE_FILE_PATH> <DESTINATION_FILE_PATH>
##### Get the process details listning to a port
    lsof -i:<PORT_NO>
##### Kill a process
    kill -9 <PROCESS_ID>
##### Find all PID and kill all

    lsof -ti :<PORT_NO> | xargs kill -9
