# Projeto-de-chat-em-grupo
Projeto de Chat em Grupo
Este projeto é uma implementação básica de um sistema de chat em grupo que inclui funcionalidades de segurança e backup. O sistema permite que membros se conectem, enviem e recebam mensagens, além de garantir a integridade dos dados através de criptografia.

Estrutura do Código
O código é dividido em várias classes, cada uma com suas responsabilidades:

1. Classe Security
Responsabilidade: Gerenciar a criptografia e a verificação de dados.
Métodos:
__init__(self, secret_key): Inicializa a classe com uma chave secreta.
encrypt_data(self, data): Criptografa os dados usando HMAC e SHA-256, e os codifica em Base64.
verify_data(self, data, encrypted_data): Verifica a integridade dos dados.
store_data(self, data): Armazena os dados criptografados em um arquivo.
retrieve_data(self): Recupera os dados criptografados do arquivo.
2. Classe GroupChat
Responsabilidade: Gerenciar um chat em grupo.
Métodos:
__init__(self, group_id): Inicializa o grupo com um ID.
add_member(self, member): Adiciona um membro ao grupo.
send_message(self, message): Envia uma mensagem para todos os membros.
receive_message(self, message): Recebe uma mensagem e a armazena.
3. Classe Member
Responsabilidade: Representar um membro do chat.
Métodos:
__init__(self, name, socket): Inicializa um membro com um nome e um socket.
connect(self, host, port): Conecta o membro a um servidor.
send(self, message): Envia uma mensagem se estiver conectado.
receive(self): Recebe uma mensagem se estiver conectado.
4. Classe Backup
Responsabilidade: Gerenciar o backup de dados.
Métodos:
backup_data(self, data): Realiza o backup dos dados usando o módulo json.
restore_data(self): Restaura os dados a partir do backup.
5. Classe Call
Responsabilidade: Gerenciar chamadas (de vídeo ou voz).
Métodos:
__init__(self, is_video_call): Inicializa a chamada.
make_call(self, host, port): Conecta a chamada a um servidor.
end_call(self): Encerra a chamada.
Como Usar
Instalação: Certifique-se de ter o Python instalado em sua máquina.
Executar o Código: Execute o arquivo Python que contém o código do chat.
Conectar Membros: Utilize a classe Member para conectar membros ao grupo de chat.
Enviar e Receber Mensagens: Utilize os métodos send_message e receive_message da classe GroupChat para comunicação entre membros.
Backup de Dados: Utilize a classe Backup para realizar o backup e a restauração dos dados.
Considerações Finais
O código é um exemplo simplificado que combina funcionalidades de chat e segurança.
A criptografia é feita usando HMAC com SHA-256, garantindo que os dados sejam protegidos.
O uso do json para backup de dados é mais seguro do que o pickle, evitando a execução de código malicioso.
Contribuições
Contribuições são bem-vindas! Sinta-se à vontade para abrir um pull request ou relatar problemas.

Licença
Este projeto está licenciado sob a MIT License - veja o arquivo LICENSE para mais detalhes.

Sinta-se à vontade para personalizar este README conforme necessário, adicionando informações específicas sobre o seu projeto ou instruções adicionais. Se precisar de mais ajuda, estou à disposição!
