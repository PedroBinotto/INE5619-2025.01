# scrathpad

### Don Banks Talk (Cisco)

- Top 10 IoT security risks (OWASP); also (any compromised, system compromised):
    - Protect Data;
    - Protect Network;
    - Protect Software/Firmware;
    - Protect Device (Hardware);

- **CIA** (Confidentiality, Integrity, Availability);

- **Threat Model:** defines what threats are being considered and which are not (ignored);

- Policy v. Mechanism, Trusted v. Trustworthy:
    - **Policy:** Specifies who/what can access which resources  under which conditions; -> **PBAC\***
    - **Mechanism:** Implements the policy;
    - **Trusted:** Responsible for maintaining security policies;
    - **Trustworthy:** Designed to be secure;

- _TCB_ and _TEE_:
    - **TCB:** _(Trusted Computing Base)_ - The hardware, software, firmware, and network componentes that must be both correct and un-corruptible in
      order to ensure that the security policy is not violated;
    - **TEE:** _(Trusted Execution Environment)_ - A secure area of the processor storage that guarantees that code
    and data located there are protected;

- Access Control (AAA), Privacy:
    - **Authentication:** _Who Are You?_;
    - **Authorization:** _What Are You Allowed to Do?_;
    - **Privacy:** A property of the data, built on top of security: the right to decide how one's information is used;
      not the same as **Confidentiality** (prevent unauthorized access);

- Categories of Fog Node Security:
    - _TEE_;
    - Data security;
    - Network security;
    - Physical security of the device;

- Trust **must** be rooted in hardware:
    - Established at _power-on_;
    - Extends chain-of-trust;
    - Firmware Hypervisor or bare-metal;

---

5. MEDIÇÕES INICIAIS

Na plataforma de monitoramento do Zabbix (frontend) foram cadastrados todos os Hosts (equipamentos monitorados da rede) e foi utilizado um template de ICMP Ping para monitorar esses equipamentos. Para cadastrar hosts clicamos em “Monitoring” na barra de navegação a esquerda e depois em “Hosts”. Uma vez na página de Hosts, clicamos no botão “Create host” no canto superior direito para cadastrar um novo dispositivo a ser monitorado. Na nova janela aberta colocamos no campo “Host name” o nome com o qual queremos identificar o dispositivo, no campo “Templates” digitamos ICMP Ping, em “Host groups” selecionamos “Discovered hosts”, em interfaces clicamos em “Add” e depois em Agent, agora colocamos o IP do dispositivo que estamos querendo monitorar no campo “IP address” e confirmamos a inclusão clicando no botão Add. Após cadastrar todos os dispositivos desejados, eles aparecerão na tela principal de Hosts como na imagem abaixo:

[Imagem]

Para que o Zabbix conseguisse “pingar” o Notebook 1 e o Notebook 2 foi necessário desativar o firewall desativar o firewall do Windows, para que não bloqueasse as requisições ICMP. Para desativar no Windows 11 segui o caminho: Configurações > Privacidade e Segurança > Segurança do Windows > Firewall e proteção de rede > Rede pública > Desativar. Foram analisadas as métricas relacionadas ao monitoramento pelo ICMP Ping para cada um dos equipamentos, através do monitoramento de loss (perda de pacote), ping e tempo de resposta. Abaixo temos os gráficos de tempo de resposta para cada um dos equipamentos monitorados: 
● Notebook 
[Imagem]
1 Observamos que o gráfico de tempo de resposta para o ping varia bastante mas sempre se mantém coletando um tempo de resposta, pois o Notebook 1 foi o equipamento utilizado para servir de hospedeiro para a VM com o Appliance do Zabbix, além de servir como dispositivo monitorado. Ele se manteve ligado e em uso o tempo inteiro durante o intervalo dessas medições. 
● Notebook 2
[Imagem]
Em relação ao Notebook 2 podemos observar que há um intervalo onde não houve a medição de tempo de resposta ao ping, isso porque esse dispositivo estava utilizando a energia da bateria e não estava sendo usado e acabou entrando em modo de hibernação, não respondendo ao ping durante esse período. 
● Smartphone
[Imagem]
O dispositivo Smartphone assim como o Notebook 2 também não estava em uso, mas diferente do Notebook 2, o smartphone não entra em hibernação. Entretanto, talvez devido a sua arquitetura e seu sistema operacional ele não respondeu aos pings, como podemos ver nos intervalos sem resposta mostrados no gráfico.
