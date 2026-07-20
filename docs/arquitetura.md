## Equipamentos de Rede

A infraestrutura utiliza equipamentos de diferentes fabricantes para representar funções de roteamento, segurança, comutação, acesso sem fio e telefonia.

| Equipamento                    | Função                                                                            |
| ------------------------------ | --------------------------------------------------------------------------------- |
| FortiGate 60E                  | Firewall e controle de segurança da rede                                          |
| Cisco 867VAE-K9                | Roteamento, distribuição de endereços IP por DHCP e tradução de endereços por NAT |
| Cisco 2620                     | Gateway de telefonia com interfaces FXS para os ramais analógicos                 |
| Cisco Catalyst WS-C2950G-24-EI | Switch de acesso                                                                  |
| Juniper EX2300-C-12T           | Switch gerenciável                                                                |
| Cisco AIR-AP1121G-A-K9         | Ponto de acesso sem fio                                                           |

---

## Topologia Geral

```text
                           Internet
                               │
                        FortiGate 60E
                               │
                      Cisco 867VAE-K9
                         DHCP e NAT
                               │
                    Infraestrutura de switching
                               │
             ┌─────────────────┼─────────────────┐
             │                 │                 │
        Servidores        Equipamentos      Rede sem fio
          Linux             de rede          Cisco Aironet
             │
             ├── Servidor de Backup
             ├── Servidor PostgreSQL
             ├── Servidor Zabbix
             └── Servidor Asterisk
                       │
                       │ Comunicação de telefonia
                       ▼
                   Cisco 2620
                  Interfaces FXS
                       │
             ┌─────────┴─────────┐
             │                   │
       Ramal analógico 1   Ramal analógico 2
```

---

## Funções de Roteamento

### Cisco 867VAE-K9

O Cisco 867VAE-K9 atua como roteador principal do laboratório. Suas funções confirmadas são:

* Distribuição de endereços IP por DHCP.
* Tradução de endereços por NAT.
* Roteamento da rede local.
* Conectividade dos dispositivos com as demais redes do ambiente.

### Cisco 2620

O Cisco 2620 é dedicado à infraestrutura de telefonia. Ele funciona como gateway entre o servidor Asterisk e os aparelhos analógicos.

Suas funções confirmadas são:

* Disponibilização de interfaces FXS.
* Conexão de dois ramais analógicos.
* Integração com o servidor Asterisk.
* Encaminhamento da comunicação de telefonia entre o Asterisk e os aparelhos conectados às portas FXS.

---

## Fluxo da Telefonia

```text
Servidor Asterisk
       │
       │ Comunicação de voz
       ▼
   Cisco 2620
       │
       ├── Porta FXS → Ramal analógico 1
       │
       └── Porta FXS → Ramal analógico 2
```

O servidor Asterisk realiza o controle lógico das chamadas, enquanto o Cisco 2620 fornece as interfaces físicas necessárias para conectar os telefones analógicos.
