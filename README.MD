# Preparando o Ambiente de Desenvolvimento
Antes de começar a desenvolver, temos que preparar o ambiente de trabalho. Seja ele com pastas, dependencias e documentação.

## Dependencias
Para gerênciar nossas dependencias vamos usar o [Poetry](https://python-poetry.org/docs/).

#### Vamos instalar o Poetry usando pipx, logo caso não tenha o pipx, instale! [Documentação Oficial caso o tutorial a baixo não resolva seu problema](https://pipx.pypa.io/stable/installation/)

Caso esteja usando linux ubuntu:
```bash
sudo apt update
sudo apt install pipx
pipx ensurepath
sudo pipx ensurepath --global # optional to allow pipx actions in global scope. See "Global installation" section below.
```
Caso esteja usando windows, você pode instalar com pip ou com Scoop.

Instalando com Scoop (caso não tenha scoop, [clique aqui](https://scoop.sh/))
```bash
scoop install pipx
pipx ensurepath
```

Instalando com pip
```bash
py -m pip install --user pipx
```

se você instalou com pip, provavelmente encontrou esse erro:
```bash
WARNING: The script pipx.exe is installed in `<USER folder>\AppData\Roaming\Python\Python3x\Scripts` which is not on PATH
```
Abra o path que apareceu para você no terminal: (o abaixo é só um exemplo )
```bash
cd `<USER folder>\AppData\Roaming\Python\Python3x\Scripts`
```

Agora basta usar o seguinte comando
```bash
.\pipx.exe ensurepath
```
Prontinho, o pipx está instalado e pronto para uso, lembre-se de reiniciar o terminal para poder testar e seja feliz

## Instalando o Poetry:
```bash
pipx install poetry
```

## Atualizando seu Poetry caso queira uma versão mais recente:
```bash
pipx upgrade poetry
```

## Caso esteja chateado, pode desisntalar o Poetry
```bash
pipx uninstall poetry
```

# Usando o Poetry para gerenciar as dependencias
Dica super importante, sempre reinicie o VS Code após instalar o Poetry antes de usalo.

Podemos ver a lista de configurações que o poetry oferece com:
```bash
poetry config --list
```

Particularmente eu prefiro que as dependencias fiquem na pasta do projeto então, vou adicionar a config local

```bash
poetry config virtualenvs.in-project true
```

Inicie o Poetry no seu projeto
```bash
poetry init
```

Se este é seu primeiro projeto com Poetry, você pode adicionar as dependencias manualmente com
```bash
poetry add nome-da-sua-dependencia
```

Se você está trabalhando em equipe e quer ligar as dependencias, use :
```bash
poetry install 
```
o Poetry vai instalar todas as dependencias em um ambiente virtual e faciliar a sua vida.
Tudo isso seguindo as informações nos arquivos **pyproject.toml** e __petry.lock__.

#### Para dividir as dependencias em grupos de produção, desenvolvimento, etc.
Podemos organizar melhor as dependencias para deixar nosso código mais limpo.

Vamos criar um grupo chamado **dev** para todas as dependencias exclusivas de desenvolvimentos como testes.
```bash
poetry add --group dev pytest
```
Para Abrir o terminal e executar suas dependencias com poetry, use
```bash
poetry shell
```

Caso queira usar o botão de compilação do vscode, use no seu terminal
```bash
.venv\Scripts\Activate
```