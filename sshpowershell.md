##### Ouvrir powershell en Adminitrator, copier le chemin du fichier sshd_config :
![ssh 1](https://github.com/user-attachments/assets/32b3b16b-7b16-41e1-acb2-a584d6968307)
##### Rajoutez les deux lignes suivantes :
   #Afin que les commandes powershell soit prisent en compte sur la machine distante
      
      Subsystem sftp sftp-server.exe
 
  #Créez le sous-système SSH destiné à héberger un processus PowerShell sur l’ordinateur distant 
     
      Subsystem powershell c:/progra~1/powershell/7/pwsh.exe -sshs -nologo
##### Sauvegardez le fichier
##### Restart le service sshd (en Administrator).
      Restart-Service ssh
##### Maintenant les commandes ssh fonctionnent celon cette syntaxe
      ssh IP@USER "powershell CMD"
##### Pour voir la politique d'execution  
         Get-ExecutionPolicy
##### Pour changer la politique (En Administrator)
         Set-ExecutionPolicy Unrestricted
















