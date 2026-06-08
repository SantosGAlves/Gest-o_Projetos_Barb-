<div align="center">

# 💈 Barbearia Premium App

**Aplicativo móvel completo para gestão e agendamento de barbearias**

[![Flutter](https://img.shields.io/badge/Flutter-3.10%2B-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?style=for-the-badge&logo=dart&logoColor=white)](https://dart.dev)
[![Firebase](https://img.shields.io/badge/Firebase-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)](https://firebase.google.com)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)
[![Status](https://img.shields.io/badge/Status-Em%20Desenvolvimento-yellow?style=for-the-badge)]()

</div>

---

## 📋 Índice

- [Sobre o Projeto](#-sobre-o-projeto)
- [Funcionalidades](#-funcionalidades)
- [Arquitetura e Estrutura](#-arquitetura-e-estrutura)
- [Stack Tecnológica](#-stack-tecnológica)
- [Pré-requisitos](#-pré-requisitos)
- [Instalação e Configuração](#-instalação-e-configuração)
- [Configurando o Firebase](#-configurando-o-firebase)
- [Como Executar](#-como-executar)
- [Scripts Disponíveis](#-scripts-disponíveis)
- [Variáveis de Ambiente](#-variáveis-de-ambiente)
- [Contribuindo](#-contribuindo)
- [Roadmap](#-roadmap)

---

## 🎯 Sobre o Projeto

O **Barbearia Premium App** é uma solução móvel de ponta a ponta desenvolvida em **Flutter**, projetada para conectar clientes aos serviços de uma barbearia de forma fluida e moderna.

O aplicativo entrega uma experiência completa — desde o cadastro do usuário até o agendamento de serviços e acompanhamento de um programa de fidelidade — com uma interface **Dark Mode** elegante e responsiva.

### O que torna este projeto especial?

- **Responsividade inteligente:** Um `ResponsiveWrapper` garante que o layout seja exibido com proporções perfeitas (máximo de 450px de largura), funcionando sem distorções mesmo em ambientes web e desktop.
- **Backend escalável:** Integração nativa com o Firebase (Auth + Firestore), permitindo sincronização em tempo real e autenticação robusta sem necessidade de servidor próprio.
- **Design System consistente:** Toda a paleta de cores, tipografia e estilos são centralizados em `AppTheme.darkTheme`, garantindo consistência visual em todas as telas.

---

## ✨ Funcionalidades

| Módulo | Descrição | Status |
|--------|-----------|--------|
| 🔐 **Autenticação** | Login e cadastro de usuários via Firebase Auth | ✅ Implementado |
| 📅 **Agendamentos** | Marcação e gestão de cortes e serviços | ✅ Implementado |
| 🛍️ **Catálogo de Produtos** | Vitrine de produtos da barbearia | ✅ Implementado |
| 🏆 **Programa de Fidelidade** | Sistema de recompensas para clientes recorrentes | ✅ Implementado |
| 🌙 **Dark Mode** | Tema escuro padronizado em todo o app | ✅ Implementado |
| 🚀 **Splash Screen** | Tela de inicialização nativa e polida | ✅ Implementado |

---

## 🏗️ Arquitetura e Estrutura

O projeto adota uma organização **feature-first** (por domínio/funcionalidade), o que facilita a escalabilidade e a manutenção independente de cada módulo.

```
├── android/                    # Configurações nativas Android
├── ios/                        # Configurações nativas iOS
├── linux/                      # Suporte a Linux Desktop
├── macos/                      # Suporte a macOS Desktop
├── web/                        # Suporte a Web (PWA)
├── windows/                    # Suporte a Windows Desktop
│
├── lib/
│   ├── core/
│   │   └── theme/
│   │       └── app_theme.dart          # Design System — cores, tipografia, tema global
│   │
│   ├── models/
│   │   └── service_model.dart          # Modelos de dados (entidades de domínio)
│   │
│   ├── screens/
│   │   ├── auth/
│   │   │   ├── login_page.dart         # Tela de Login
│   │   │   └── register_page.dart      # Tela de Cadastro
│   │   │
│   │   ├── bookings/
│   │   │   └── booking_page.dart       # Agendamento de serviços
│   │   │
│   │   ├── home/
│   │   │   ├── home_page.dart          # Dashboard principal
│   │   │   ├── loyalty_page.dart       # Programa de Fidelidade
│   │   │   └── products_page.dart      # Catálogo de Produtos
│   │   │
│   │   └── splash/
│   │       └── splash_tela.dart        # Tela de transição animada inicial
│   │
│   ├── firebase_options.dart           # Config. gerada pelo FlutterFire CLI (não editar manualmente)
│   └── main.dart                       # Entrypoint da aplicação
│
├── firebase.json                       # Configuração do Firebase Hosting/Emulator
├── pubspec.yaml                        # Dependências e metadados do projeto
└── analysis_options.yaml               # Regras de lint (flutter_lints)
```

---

## 🛠️ Stack Tecnológica

### Core

| Tecnologia | Versão | Finalidade |
|------------|--------|------------|
| [Flutter](https://flutter.dev) | `>=3.10.0 <4.0.0` | Framework principal (UI cross-platform) |
| [Dart](https://dart.dev) | SDK compatível | Linguagem de programação |

### Firebase (Backend-as-a-Service)

| Pacote | Versão | Finalidade |
|--------|--------|------------|
| `firebase_core` | `^4.7.0` | Inicialização e configuração do ecossistema Firebase |
| `firebase_auth` | `^6.4.0` | Autenticação de usuários (e-mail/senha, OAuth) |
| `cloud_firestore` | `^6.3.0` | Banco de dados NoSQL em tempo real |

### UI & Utilitários

| Pacote | Versão | Finalidade |
|--------|--------|------------|
| `flutter_native_splash` | `^2.4.7` | Splash screen nativa para Android e iOS |
| `intl` | `^0.20.2` | Internacionalização e formatação de datas/moedas |

### Dev Dependencies

| Pacote | Finalidade |
|--------|------------|
| `flutter_lints` | Análise estática e boas práticas de código |
| `flutter_test` | Framework de testes unitários e de widgets |

---

## 📦 Pré-requisitos

Antes de começar, certifique-se de ter as seguintes ferramentas instaladas e configuradas:

- **Flutter SDK** `>=3.10.0` — [Guia de instalação oficial](https://docs.flutter.dev/get-started/install)
- **Dart SDK** — Incluído com o Flutter
- **Git** — Para clonar o repositório
- **Android Studio** ou **VS Code** com as extensões Flutter/Dart
- **Conta no Firebase** — [console.firebase.google.com](https://console.firebase.google.com)
- **FlutterFire CLI** — Para configuração do Firebase

Para verificar se seu ambiente está pronto, execute:

```bash
flutter doctor
```

Todos os itens relevantes devem estar marcados com `✓`.

---

## 🚀 Instalação e Configuração

### 1. Clone o repositório

```bash
git clone https://github.com/SantosGAlves/Gest-o_Projetos_Barb-.git
cd Gest-o_Projetos_Barb-
```

### 2. Instale as dependências

```bash
flutter pub get
```

### 3. Gere a Splash Screen nativa

Após instalar as dependências, gere os assets da splash screen para as plataformas nativas:

```bash
dart run flutter_native_splash:create
```

---

## 🔥 Configurando o Firebase

Este projeto utiliza o Firebase como backend. Você precisará criar seu próprio projeto no Firebase e conectá-lo à aplicação.

### Passo 1 — Instale o FlutterFire CLI

```bash
dart pub global activate flutterfire_cli
```

### Passo 2 — Crie um projeto no Firebase Console

Acesse [console.firebase.google.com](https://console.firebase.google.com), crie um novo projeto e ative os seguintes serviços:

- **Authentication** → habilite o provedor "E-mail/Senha"
- **Cloud Firestore** → crie um banco de dados (comece no modo de teste para desenvolvimento)

### Passo 3 — Configure o FlutterFire no projeto

Na raiz do projeto, execute:

```bash
flutterfire configure
```

Selecione seu projeto Firebase e as plataformas desejadas (Android, iOS, Web). O comando irá gerar ou atualizar automaticamente o arquivo `lib/firebase_options.dart`.

> ⚠️ **Atenção:** O arquivo `firebase_options.dart` contém chaves de API e **não deve ser commitado** em repositórios públicos em produção. Considere adicioná-lo ao `.gitignore` e gerenciá-lo via variáveis de ambiente em pipelines de CI/CD.

### Passo 4 — Regras de segurança do Firestore

Para desenvolvimento, configure as regras do Firestore para permitir leitura e escrita autenticada:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.auth != null;
    }
  }
}
```

> ⚠️ Em produção, substitua por regras granulares e restritivas por coleção.

---

## ▶️ Como Executar

### Verificar dispositivos disponíveis

```bash
flutter devices
```

### Executar no emulador/dispositivo Android

```bash
flutter run
```

### Executar no simulador iOS (apenas macOS)

```bash
flutter run -d ios
```

### Executar na Web

```bash
flutter run -d chrome
```

### Executar no modo release (produção)

```bash
flutter run --release
```

---

## 📜 Scripts Disponíveis

| Comando | Descrição |
|---------|-----------|
| `flutter pub get` | Instala todas as dependências |
| `flutter run` | Inicia o app em modo debug |
| `flutter run --release` | Inicia o app em modo release |
| `flutter build apk` | Gera o APK para Android |
| `flutter build apk --release` | Gera o APK otimizado para produção |
| `flutter build ios` | Compila para iOS (requer macOS + Xcode) |
| `flutter build web` | Compila para Web |
| `flutter test` | Executa todos os testes |
| `flutter analyze` | Roda a análise estática de código (lint) |
| `dart run flutter_native_splash:create` | Regenera a splash screen nativa |

---

## 🔐 Variáveis de Ambiente

Este projeto não utiliza um arquivo `.env` convencional. As configurações sensíveis do Firebase são gerenciadas pelo `firebase_options.dart`, gerado pelo FlutterFire CLI.

Para diferentes ambientes (dev, staging, prod), a abordagem recomendada é:

1. Criar projetos Firebase separados (ex: `barbearia-dev` e `barbearia-prod`)
2. Manter arquivos `firebase_options_dev.dart` e `firebase_options_prod.dart`
3. Usar `--dart-define` ou flavors do Flutter para selecionar o ambiente no build

---

## 🤝 Contribuindo

Contribuições são bem-vindas! Para manter a qualidade do código, siga o fluxo abaixo:

1. **Fork** este repositório
2. Crie uma branch para sua feature:
   ```bash
   git checkout -b feature/nome-da-sua-feature
   ```
3. Faça seus commits seguindo [Conventional Commits](https://www.conventionalcommits.org/pt-br/v1.0.0/):
   ```bash
   git commit -m "feat: adiciona tela de histórico de agendamentos"
   ```
4. Certifique-se de que o código passa na análise estática:
   ```bash
   flutter analyze
   flutter test
   ```
5. Abra um **Pull Request** descrevendo as mudanças realizadas

---

## 🗺️ Roadmap

- [ ] Notificações push para lembretes de agendamento
- [ ] Integração com pagamento in-app (PIX / cartão)
- [ ] Painel administrativo para o barbeiro
- [ ] Avaliações e reviews de serviços
- [ ] Histórico completo de agendamentos
- [ ] Suporte a múltiplas unidades da barbearia
- [ ] Testes unitários e de integração

---

Feito com ❤️ e Flutter

</div>
