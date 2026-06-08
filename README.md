# 💈 Barbearia Premium App

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-%2302569B.svg?style=for-the-badge&logo=Flutter&logoColor=white" alt="Flutter" />
  <img src="https://img.shields.io/badge/Firebase-%23FFCA28.svg?style=for-the-badge&logo=firebase&logoColor=black" alt="Firebase" />
  <img src="https://img.shields.io/badge/Dart-%230175C2.svg?style=for-the-badge&logo=dart&logoColor=white" alt="Dart" />
</p>

> Uma aplicação móvel elegante e de alta performance para gestão e agendamento de barbearias, desenvolvida com foco em uma experiência de usuário (UI/UX) limpa, moderna e com estética nativa em *dark mode*.

## 📱 Visão Geral

O **Barbearia Premium App** é uma solução completa desenvolvida em Flutter para conectar clientes aos serviços de uma barbearia. O projeto inclui um fluxo completo de autenticação, agendamento de serviços, visualização de produtos e programa de fidelidade. A arquitetura foi pensada para manter a consistência visual em diferentes telas, utilizando um `ResponsiveWrapper` que garante proporções perfeitas (limite de 450px de largura) mesmo quando executado na web ou desktop.

## ✨ Funcionalidades Principais

* **Autenticação Segura:** Login e registro de usuários integrados ao Firebase Authentication.
* **Agendamentos (Bookings):** Interface dedicada para marcação de cortes e serviços.
* **Catálogo de Produtos:** Vitrine de produtos da barbearia disponíveis para os clientes.
* **Programa de Fidelidade (Loyalty):** Sistema de recompensas e acompanhamento para clientes recorrentes.
* **Design Premium:** Estilo *Dark Theme* padronizado em todo o aplicativo (`AppTheme.darkTheme`).
* **Splash Screen Nativa:** Inicialização polida e responsiva utilizando o pacote `flutter_native_splash`.

## 🛠️ Tecnologias e Dependências

O projeto utiliza o SDK do Flutter (`>=3.10.0 <4.0.0`) e depende dos seguintes pacotes essenciais:

* **[firebase_core](https://pub.dev/packages/firebase_core) (^4.7.0):** Inicialização do ecossistema Firebase.
* **[firebase_auth](https://pub.dev/packages/firebase_auth) (^6.4.0):** Gerenciamento de sessões e autenticação.
* **[cloud_firestore](https://pub.dev/packages/cloud_firestore) (^6.3.0):** Banco de dados NoSQL em tempo real para armazenar agendamentos, usuários e produtos.
* **[flutter_native_splash](https://pub.dev/packages/flutter_native_splash) (^2.4.7):** Geração de telas de abertura nativas para Android e iOS.
* **[intl](https://pub.dev/packages/intl) (^0.20.2):** Internacionalização e formatação de datas (essencial para o módulo de agendamentos).

## 📁 Estrutura de Diretórios (Main)

A arquitetura do projeto na pasta `lib/` foi modularizada por domínios/features para facilitar a manutenção e escalabilidade:

```text
lib/
├── core/
│   └── theme/
│       └── app_theme.dart       # Definições globais de design (Dark Mode)
├── models/
│   └── service_model.dart       # Modelos de dados
├── screens/
│   ├── auth/
│   │   ├── login_page.dart      # Tela de Autenticação
│   │   └── register_page.dart   # Tela de Cadastro
│   ├── bookings/
│   │   └── booking_page.dart    # Lógica e UI de Agendamentos
│   ├── home/
│   │   ├── home_page.dart       # Dashboard Principal
│   │   ├── loyalty_page.dart    # Tela de Fidelidade
│   │   └── products_page.dart   # Vitrine de Produtos
│   └── splash/
│       └── splash_tela.dart     # Tela de transição animada inicial
├── firebase_options.dart        # Configurações geradas pelo FlutterFire CLI
└── main.dart                    # Ponto de entrada (Entrypoint)
