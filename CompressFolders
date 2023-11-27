<# This script uses 7zip to compress multiple subfolders 
and saves them individually in separate zip files.
#>
 
# Specify source folder
$source = Read-Host "FOLDER CONTAINING FOLDERS (EG C:\SOURCE)"
 
# Specify zip file location folder (destination folder, make sure it exists)
$destination = Read-Host "DESTINATION WHERE ZIPPED FILES WILL BE (C:\DEST)"

$zipPath = "C:\Program Files\7-Zip\7z.exe"
 
# Action
$subfolders = Get-ChildItem $source -Directory


foreach ($s in $subfolders) {
 
$folderpath = $s.FullName
$foldername = $s.Name
 
$fulldest = $destination+"\"+$foldername
$destnofolder= $destination+"\"
$sourcenofolder=$folderpath +"\*.*"

$parameters = "a -r -tzip `"$fulldest`" `"$sourcenofolder`""

Start-Process $zipPath -ArgumentList $parameters -wait

}
