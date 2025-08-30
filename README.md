# projeto-az-dio
# **Criação de Máquina Virtual no Microsoft Azure**

Este documento descreve as etapas e configurações utilizadas para a criação de uma **Máquina Virtual (VM)** no **Microsoft Azure**, utilizando o sistema operacional **Ubuntu Server 24.04 LTS**. As capturas de tela anexadas mostram cada fase do processo, desde a configuração inicial até a revisão e validação final.

---

## ✅ **1. Objetivo**
Criar uma máquina virtual baseada em Linux (**Ubuntu Server**) no **Microsoft Azure** para estudos, testes e desenvolvimento como projeto da dio.

---

## ✅ **2. Configurações Gerais**
### **Assinatura e Grupo de Recursos**
- **Assinatura:** Azure subscription 1
- **Grupo de recursos:** `estudo` 

### **Nome e Região**
- **Nome da VM:** `azLinux`
- **Região:** `(Europe) Switzerland North` (Configuração padrão na seção da plataforma)

---

## ✅ **3. Configurações da Instância**
- **Opções de disponibilidade:** Zona de disponibilidade
- **Opções de zona:** Zona auto-selecionada
- **Zona de disponibilidade:** Zona 1
- **Tipo de segurança:** Computadores virtuais de inicialização confiável
- **Habilitar inicialização segura:** Sim
- **Habilitar vTPM:** Sim
- **Monitoramento de integridade:** Não
- **Imagem do SO:** **Ubuntu Server 24.04 LTS – Gen2**
- **Arquitetura:** x64
- **Tamanho da VM:** **Standard B1s** (1 vCPU, 1 GiB RAM)
- **Hibernação:** Não
- **Tipo de autenticação:** **Chave pública SSH**
- **Usuário padrão:** `azureuser`
- **Formato da chave SSH:** RSA
- **Nome do par de chaves:** `azLinux_key`
- **Portas públicas:** SSH (22)
- **Azure Spot:** Não habilitado

---

## ✅ **4. Configurações de Disco**
- **Tipo de disco do SO:** LRS do SSD Premium
- **Tamanho:** Padrão da imagem
- **Discos gerenciados:** Sim
- **Excluir disco do SO ao excluir VM:** Habilitado
- **Disco efêmero:** Não habilitado

---

## ✅ **5. Configurações de Rede**
- **Rede virtual:** `azLinux-vnet`
- **Sub-rede:** `default (10.0.0.0/24)`
- **IP público:** Criado novo
- **Grupo de segurança:** Básico
- **Portas permitidas:** SSH (22)
- **Rede acelerada:** Desativada
- **Balanceamento de carga:** Não configurado

⚠️ **Aviso:** As portas SSH estão abertas para a Internet. **Recomendado apenas para testes!**

---

## ✅ **6. Gerenciamento**
- **Microsoft Defender para Nuvem:** Básico (gratuito)
- **Identidade gerenciada:** Desativada
- **Backup:** Desativado
- **Desligamento automático:** Desativado
- **Patch dinâmico:** Desativado
- **Orquestração de patch:** Padrão da imagem

---

## ✅ **7. Monitoramento**
- **Alertas:** Desativados
- **Diagnóstico de inicialização:** Ativado
- **Diagnóstico do convidado do SO:** Desativado

---

## ✅ **8. Avançado**
- **Extensões:** Nenhuma
- **Aplicativos de VM:** Nenhum
- **Cloud-init:** Não configurado
- **Controlador de disco:** SCSI
- **Posicionamento por proximidade:** Nenhum
- **Reserva de capacidade:** Nenhum

---

## ✅ **9. Marcas (Tags)**
As marcas foram utilizadas para organização e identificação dos recursos:
```
Nome: estudar
Valor: azLinux
```
Recursos marcados:
- Máquina virtual
- Disco
- Endereço IP público
- Grupo de segurança de rede
- Interface de rede
- Rede virtual
- Conjunto de disponibilidade
- Chave SSH
- Cofre de serviços de recuperação
- Extensão da VM
- SQL Virtual Machine (placeholder)

---

## ✅ **10. Preço Estimado**
- **Tipo de Instância:** Standard B1s
- **Preço:** **0,0132 USD/hora** (aproximadamente 9,50 USD/mês)

---

## ✅ **11. Resumo Final da Configuração**
- **Nome da VM:** azLinux
- **SO:** Ubuntu Server 24.04 LTS – Gen2
- **Tamanho:** Standard B1s (1 vCPU, 1 GiB RAM)
- **Autenticação:** SSH (chave pública)
- **Porta aberta:** 22 (SSH)
- **Disco:** SSD Premium
- **Região:** Switzerland North
- **Grupo de Recursos:** estudo

---

## ✅ **12. Observações Importantes**
- **Segurança:** É fortemente recomendado configurar **NSG (Network Security Group)** para limitar IPs confiáveis no acesso SSH.
- **Custo:** A instância escolhida é de baixo custo, ideal para testes, mas com recursos limitados.
- **Escalabilidade:** Caso necessário, será possível redimensionar a VM no futuro.
- **Backup:** Considere habilitar backup para ambientes de produção.

---

## 🔗 **Links Úteis**
- [Documentação oficial do Azure](https://learn.microsoft.com/azure)
- [Preços de máquinas virtuais Azure](https://azure.microsoft.com/pricing/details/virtual-machines/)
- [Configuração de SSH no Azure](https://learn.microsoft.com/azure/virtual-machines/linux/ssh-from-windows)
- [Imagens](/images/)

---

### ✅ **Status: Validação aprovada e pronta para criação**

## ✅ Conclusão
O processo de criação de VM na Azure é bem simples e intuitivo, porém, para configurar de forma adequada para as suas necessidades, é importante observar se os custos estarão de acordo com suas expectativas. Tanto para projetos de testes quanto para projetos reais. É importante destacar que existem diversas formas de configuração para as mesmas necessidades e que, dependendo das opções escolhidas, também serão influenciadas questões sobre a responsabilidade compartilhada de segurança, podendo trazer mais responsabilidades para o contratante quando este tem maior controle sobre a infraestrutura. O importante é sempre fazer uma boa análise sobre quais são as reais necessidades de cada projeto para que os riscos sejam sempre mitigados e que o mínimo de falhas ocorra, bem como o mínimo de custos com os melhores benefícios seja escolhido. 