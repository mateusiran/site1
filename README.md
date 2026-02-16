
# Criando _config.yml para GitHub Pages
config_yml = """# Configuração do GitHub Pages
title: Marketplace Brasil
description: Sistema completo de e-commerce inspirado no Mercado Livre e Shopee
baseurl: "/marketplace-brasil"
url: "https://seu-usuario.github.io"

# Configurações de build
markdown: kramdown
highlighter: rouge
permalink: pretty

# Excluir arquivos do build
exclude:
  - README.md
  - .gitignore
  - Gemfile
  - Gemfile.lock
"""

with open(os.path.join(base_path, "_config.yml"), "w", encoding="utf-8") as f:
    f.write(config_yml)

# Criar .gitignore
gitignore = """# Dependencies
node_modules/

# Build files
_site/
.sass-cache/
.jekyll-cache/
.jekyll-metadata

# IDE
.vscode/
.idea/
*.swp
*.swo

# OS
.DS_Store
Thumbs.db

# Logs
*.log
"""

with open(os.path.join(base_path, ".gitignore"), "w", encoding="utf-8") as f:
    f.write(gitignore)

print("✅ _config.yml criado!")
print("✅ .gitignore criado!")

# Listar todos os arquivos criados
print("\n📁 Estrutura final do projeto:")
for root, dirs, files in os.walk(base_path):
    level = root.replace(base_path, '').count(os.sep)
    indent = ' ' * 2 * level
    print(f'{indent}{os.path.basename(root)}/')
    subindent = ' ' * 2 * (level + 1)
    for file in files:
        print(f'{subindent}{file}')