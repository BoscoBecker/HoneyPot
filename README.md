# Honeypot PHP - Proteção contra bots e intrusos

Este é um script simples de honeypot desenvolvido em PHP, projetado para detectar e registrar acessos suspeitos e tentativas de acesso maliciosas em uma aplicação web. Ele armazena informações valiosas sobre cada tentativa, como o endereço IP, a geolocalização do visitante, o agente de usuário e outros cabeçalhos, ajudando a proteger seu sistema contra bots e intrusos.

🍯 **O que é um Honeypot?**

Um honeypot é uma técnica de segurança utilizada para enganar bots e atacantes, fazendo com que eles interajam com recursos falsos ou inutilizáveis, enquanto o sistema real permanece seguro e monitorado. No caso deste script, ele registra informações sobre os visitantes que tentam acessar áreas críticas do site.

---

### Funcionalidades:
- **Registro de IP:** Armazena o endereço IP de cada tentativa de acesso.
- **Geolocalização:** Obtém informações sobre a localização geográfica do visitante, como país e cidade.
- **Detecção de Proxy e VPN:** Identifica se o visitante está usando um proxy ou VPN.
- **Contagem de tentativas:** Conta quantas vezes um IP tentou acessar a página.
- **Logs detalhados:** Registra o agente de usuário e cabeçalhos HTTP para análise.

---

### Como funciona:

1. **Acessos à Página:** O script é configurado para monitorar acessos à página `/wp-admin.php` (mas pode ser adaptado para outras URLs).
2. **Geolocalização do IP:** Usando a API `ip-api.com`, o script tenta descobrir a localização do visitante.
3. **Verificação de Proxy e VPN:** Também verifica se o visitante está usando serviços de proxy ou VPN.
4. **Contagem de Acessos:** Mantém um registro de quantas vezes o mesmo IP tentou acessar a página monitorada.

---

### Como usar:

1. **Crie o arquivo de log:** Assegure-se de que o caminho para o arquivo de log (`honeypot_log.txt`) seja seguro e esteja fora do diretório `public_html` (se possível).
   
2. **Coloque o script no seu servidor:** Coloque este código PHP em uma página do seu site que você deseja monitorar. No exemplo acima, ele está configurado para monitorar a página `/wp-admin.php`.

3. **Verifique os logs:** O arquivo de log gerado (`honeypot_log.txt`) armazenará todas as tentativas de acesso com informações detalhadas sobre cada visitante.

---

### Exemplo de entrada no log:

Page: /wp-admin.php 2025-03-28 10:00:00 - IP: 192.168.1.1 - País: Brasil - Cidade: São Paulo - ISP: Vivo - Proxy: NÃO - VPN: NÃO - Acessos: 2 - Agent: Mozilla/5.0 (...) - Headers: { "Header1": "Value1", "Header2": "Value2" }


---

### Considerações:
- **Segurança:** Este script ajuda a identificar padrões de comportamento e pode ser útil para proteger seu sistema de bots e outras ameaças.
- **Armazenamento de Dados:** Tenha em mente que o armazenamento de informações pessoais, como endereços IP, pode estar sujeito a regulamentações locais de privacidade, como o GDPR.
- **Melhorias:** Você pode expandir o script para adicionar mais camadas de verificação, como captchas ou bloqueios automáticos para IPs suspeitos.

---

### Emojis: 🍯🐝

Utilize este honeypot como uma "armadilha doce" para pegar os bots e intrusos enquanto mantém seu sistema seguro!

---

### License:
Este script é fornecido gratuitamente para fins educativos e de segurança, sem garantia de qualquer tipo.
