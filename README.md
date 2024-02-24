# SpotMusic - Music Library Service

O `spotmusic-music-library-service` é um componente crítico da aplicação SpotMusic, responsável pelo gerenciamento da biblioteca de músicas. Este serviço permite a criação, consulta, atualização e exclusão de músicas e álbuns, fornecendo uma interface robusta e escalável para o armazenamento de dados musicais.

## Pilha Tecnológica
- **Linguagem de Programação:** Python com Flask
- **Banco de Dados:** MySQL (Nome do Banco: `spotmusic_library`)
- **Cache:** Redis (Para armazenamento de dados de acesso rápido)
- **Monitoramento:** Zabbix (Para monitoramento do desempenho do serviço)

## Configuração e Instalação
Para configurar e executar o `spotmusic-music-library-service` localmente, siga os passos abaixo:

```bash
# Clone o repositório
git clone https://github.com/fiap-spotmusic/spotmusic-music-library-service.git
cd spotmusic-music-library-service

# Instale as dependências
pip install -r requirements.txt

# Copie o arquivo .env.template, cole como .env e substitua as variáveis apontando para o ambiente desejado
cp .env.template .env
# Agora, edite o arquivo .env com as configurações do seu ambiente
nano .env

# Carregue as variáveis de ambiente
export $(cat .env | xargs)

# Execute as migrações para o banco de dados
flask db upgrade

# Inicie o serviço
flask run
