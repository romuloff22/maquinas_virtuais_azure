# **Roteiro de Aprendizagem - Certificação Microsoft AZ-104**  

## **Visão Geral**  
Este documento descreve os principais tópicos estudados para a certificação **Microsoft AZ-104 (Microsoft Azure Administrator)**, com foco em **Máquinas Virtuais (VMs)**, **armazenamento**, **disponibilidade** e **escalabilidade** no Azure.  

---

## **1. Configurando Máquinas Virtuais no Azure**  

### **1.1. Responsabilidades dos Serviços de Nuvem**  
✔ **Modelo de responsabilidade compartilhada**:  
   - **Azure**: Responsável pela infraestrutura física, rede e datacenters.  
   - **Cliente**: Responsável por configurar VMs, atualizações de SO, segurança e dados.  

✔ **Diferença entre IaaS, PaaS e SaaS**:  
   - **IaaS (Infra as a Service)**: Controle total sobre VMs (ex: Azure VMs).  
   - **PaaS (Platform as a Service)**: Azure gerencia infraestrutura (ex: Azure App Service).  
   - **SaaS (Software as a Service)**: Aplicativos prontos (ex: Office 365).  

### **1.2. Planejando Máquinas Virtuais**  
✔ **Seleção de tamanho da VM**:  
   - **Propósito geral (B-series, D-series)**: Balanceamento entre CPU e memória.  
   - **Computação otimizada (F-series)**: Alta performance em CPU.  
   - **Memória otimizada (E-series)**: Bancos de dados e aplicações em memória.  
![Captura de tela de 2025-06-20 17-57-28](https://github.com/user-attachments/assets/757bad77-3094-4f0d-a648-7f99d04b1dab)

✔ **Escolha de imagem (OS)**:  
   - Windows Server, Linux (Ubuntu, CentOS, Red Hat).  
   - Imagens pré-configuradas (SQL Server, SAP HANA).
![Captura de tela de 2025-06-20 17-59-20](https://github.com/user-attachments/assets/5fb4ef3f-d624-4c92-9443-c9b52e45a133)
 

### **1.3. Armazenamento da Máquina Virtual**  
✔ **Tipos de discos**:  
   - **SSD Premium (P-series)**: Alta performance (IOPS e throughput).  
   - **SSD Standard (E-series)**: Custo-benefício para cargas moderadas.  
   - **HDD Standard (S-series)**: Armazenamento econômico para backups.  
![Captura de tela de 2025-06-20 18-00-44](https://github.com/user-attachments/assets/a1590c35-4b46-492a-9cd5-c4d2ca02dce9)

✔ **Criação, Anexação e Desanexação de Discos**  
   - **Criação de discos**: Criando discos para serem anexados a máquina virtual.
   - **Anexando discos**: Anexando disco a quente, se precisar reinciar a máquina virtual.
   - **Desanexando discos**: Desanexando disco a quente, se precisar reinciar a máquina virtual.
![Captura de tela de 2025-06-20 18-01-47](https://github.com/user-attachments/assets/0f4a0a9d-e3e5-4848-953b-203798228d4d)

### **1.4. Conectando-se às Máquinas Virtuais**  
✔ **Métodos de conexão**:  
   - **RDP (Windows)**: Usando `mstsc` ou portal Azure.  
   - **SSH (Linux)**: Via terminal (ex: `ssh user@ip-da-vm`).  
   - **Bastion Host**: Acesso seguro via navegador.  

✔ **Configuração de NSG (Network Security Group)**:  
   - Regras de entrada/saída para RDP/SSH (portas 3389/22).
![Captura de tela de 2025-06-20 18-02-18](https://github.com/user-attachments/assets/3f28a0e6-4aff-4660-9125-f03972951928)


### **1.5. Disk Encryption (Criptografia de Discos)**  
✔ **Azure Disk Encryption (ADE)**:  
   - Usa **BitLocker (Windows)** ou **DM-Crypt (Linux)**.  
   - Integrado com **Azure Key Vault** para armazenar chaves.  
![Captura de tela de 2025-06-20 18-03-43](https://github.com/user-attachments/assets/66795ce9-571e-481a-8e51-2d199ae1f251)

---

## **2. Configurando Disponibilidade da Máquina Virtual**  

### **2.1. Planejando Manutenção e Tempo de Inatividade**  
✔ **Tipos de manutenção**:  
   - **Planejada**: Atualizações do Azure (notificação prévia).  
   - **Não planejada**: Falhas de hardware/rede.  

✔ **SLAs (Service Level Agreements)**:  
   - **99,9%** para VMs únicas.  
   - **99,95%** para VMs em Availability Sets.  

### **2.2. Configurando Conjuntos de Disponibilidade (Availability Sets)**  
✔ **Objetivo**: Evitar downtime distribuindo VMs em:  
   - **Domínios de Falha (FD)**: Evita falhas simultâneas (ex: rack diferente).  
   - **Domínios de Atualização (UD)**: Atualiza uma VM por vez.  
![Captura de tela de 2025-06-20 18-04-48](https://github.com/user-attachments/assets/381e705a-76d6-42ab-a80f-75da3e8014f2)


### **2.3. Zonas de Disponibilidade (Availability Zones)**  
✔ **Funcionamento**:  
   - VMs distribuídas em **datacenters fisicamente separados**.  
   - **3+ zonas por região** (ex: East US - Zonas 1, 2, 3).  
![Captura de tela de 2025-06-20 18-06-48](https://github.com/user-attachments/assets/64772977-842b-4c5e-91dd-efafc0a7bda1)


### **2.4. Escalabilidade (Vertical vs. Horizontal)**  
✔ **Escala Vertical**: Aumentar recursos da VM (ex: de B2s para B4ms).  
✔ **Escala Horizontal**: Adicionar mais VMs (**Virtual Machine Scale Sets - VMSS**).  
![Captura de tela de 2025-06-20 18-07-35](https://github.com/user-attachments/assets/9e658fcf-6435-48bd-b739-fb680caaa69d)

---

## **3. Revisão e Prática**  

### **3.1. Exercícios Práticos Realizados**  
✅ **Criar uma VM do zero** (Portal Azure/CLI).  
✅ **Configurar Disk Encryption** (Azure Key Vault + BitLocker).  
✅ **Implementar Availability Sets e VM Scale Sets**.  
✅ **Testar failover entre zonas de disponibilidade**.  
