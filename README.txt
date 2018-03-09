https://repo1.maven.org/maven2/com/profesorfalken/jPowerShell/1.9.1/jPowerShell-1.9.1.jar
Enter-PSSession -ComputerName SERVIDOR1 -Credential GRUPOZANARDO\Administrador
https://www.joaoheytor.com/2016/07/08/powershell-habilitando-conexao-remota/

Import-Module ActiveDirectory
New-ADUser -Path 'OU=Matriz,dc=GRUPOZANARDO,dc=LOCAL' -Name teste -UserPrincipalName teste@GRUPOZANARDO.LOCAL -GivenName teste -DisplayName "teste" -AccountPassword (ConvertTo-SecureString -AsPlainText "12345678" -Force) -Enabled $True
https://www.microsoft.com/pt-br/download/details.aspx?id=7887