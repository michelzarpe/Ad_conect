https://repo1.maven.org/maven2/com/profesorfalken/jPowerShell/1.9.1/jPowerShell-1.9.1.jar
Enter-PSSession -ComputerName SERVIDOR1 -Credential GRUPOZANARDO\Administrador
https://www.joaoheytor.com/2016/07/08/powershell-habilitando-conexao-remota/

Import-Module ActiveDirectory
New-ADUser -Path 'OU=Matriz,dc=GRUPOZANARDO,dc=LOCAL' -Name teste -UserPrincipalName teste@GRUPOZANARDO.LOCAL -GivenName teste -DisplayName "teste" -AccountPassword (ConvertTo-SecureString -AsPlainText "12345678" -Force) -Enabled $True
https://www.microsoft.com/pt-br/download/details.aspx?id=7887


import javax.swing.JOptionPane;

import com.authy.*;
import com.authy.api.*;

public class Executando {

	public static void main(String[] args) {
		
		AuthyApiClient client = new AuthyApiClient("5498465438464sdf4a6df48asdf48ad8sd");
		Users users = client.getUsers();
		
		Tokens tokens = client.getTokens();
		String token = JOptionPane.showInputDialog("Digite Aqui: ");  
		Token verification = tokens.verify(546545, token);
		System.out.println(verification.isOk());
		
		//Criar novo usuario Token
		User user = users.createUser("561684@gmail.com", "56498484", "55");
		System.out.println(user.getId());
		
		//Deletar Usuario
		Hash response = users.deleteUser(75827890);
		System.out.println(response.isOk());
			
		//Validar Token 
		//Tokens tokens = client.getTokens();
		//Token verification = tokens.verify(76048082, "1040865");
		System.out.println(verification.isOk());
		
		//Enviar ligação para usuario cadastrado com token
		Hash call = users.requestCall(76048082);
		
		//Enviar SMS para usuario cadastrado com token
		Hash sms = users.requestSms(76048082);
		System.out.println(sms.isOk());
		
	}

}
