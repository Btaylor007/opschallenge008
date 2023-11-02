# opschallenge008
cho off To dispay the command being given
setlocal enabledelayedexpansion

set /p sourcePath=Enter the source folder path:  set is the command and /p is the directory where you want the path to delete files from 

set /p destinationPath=Enter the destination folder path:

if not exist "!sourcePath!\" (
    echo Error: Source folder does not exist. This is saying that if the file to be looked for isnt found echo source not found and then go to 
    goto :eof goes to the label :eof
)

if not exist "!destinationPath!\" ( if this file path doesn't exist tell user destination folder doesn't exist then goto eof
    echo Error: Destination folder does not exist.
    goto :eof
)

robocopy "!sourcePath!" "!destinationPath!" /E back up theses files 

if errorlevel 8 (
    echo Error: ROBOCOPY encountered errors during the copy operation. if error level 8 occurs at this level tell user error occured or tell your robocopy was successful  
) else (
    echo Copy operation completed successfully.
)

:end
endlocal the end of script 
