# ViteReact com Capacitor

## Passo 1: Configurar o Projeto Vite
Crie um novo projeto Vite:

    npm create vite@latest my-vite-app
    cd my-vite-app
    npm install
    
## Verifique se o projeto Vite está funcionando:

    npm run dev
    
## Passo 2: Instalar Capacitor
Adicione Capacitor ao seu projeto:

    npm install @capacitor/core @capacitor/cli
    
## Inicialize Capacitor no seu projeto:

    npx cap init [appName] [appId]
    
Substitua [appName] pelo nome da sua aplicação e [appId] por um identificador único (ex.: com.exemplo.app).

## Passo 3: Configurar Capacitor
Adicione a plataforma Android:

    npm install @capacitor/android
    npx cap add android
    
Adicione a plataforma iOS:

    npm install @capacitor/ios
    npx cap add ios
    
## Passo 4: Construir o Projeto Vite
Construa o seu projeto Vite:

    npm run build
    
Copie os arquivos de build para o Capacitor:

    npx cap copy
    
## Passo 5: Abrir e Configurar Plataformas Nativas (Android e iOS)
Abra o projeto Android no Android Studio:

    npx cap open android
    
No Android Studio, você pode compilar e executar a aplicação no emulador ou em um dispositivo físico.

Abra o projeto iOS no Xcode (necessário estar em um macOS):

    npx cap open ios
    
No Xcode, você pode compilar e executar a aplicação no simulador ou em um dispositivo físico.

## Passo 6: Configurar Capacitor para a Produção
Ajuste as configurações de Capacitor no arquivo capacitor.config.ts (ou capacitor.config.json):

    import { CapacitorConfig } from '@capacitor/cli';

        const config: CapacitorConfig = {
        appId: 'com.exemplo.app',
        appName: 'MyViteApp',
        webDir: 'dist',  // Certifique-se de que o diretório de saída está correto
        bundledWebRuntime: false
    };
    export default config;

Verifique se o arquivo de configuração do Capacitor (capacitor.config.ts ou capacitor.config.json) está apontando para o diretório correto de build (dist no caso do Vite).

## Passo 7: Testar e Distribuir
Teste sua aplicação no Android:

No Android Studio, clique em "Run" para compilar e executar a aplicação no emulador ou em um dispositivo físico.
Teste sua aplicação no iOS:

No Xcode, selecione um dispositivo ou simulador e clique no botão "Play" para compilar e executar a aplicação.
Distribuir sua aplicação:

Para Android: Compile um APK ou AAB no Android Studio e faça o upload para a Google Play Store.
Para iOS: Archive a aplicação no Xcode e faça o upload para a App Store usando o App Store Connect.

# Atualizar projeto no Android Studio e Xcode

## Passo a Passo para Atualizar o Projeto no Android Studio

### Construir novamente o projeto Vite:
Primeiro, sempre que você fizer alterações no seu código Vite, você precisa construir novamente o projeto Vite para gerar os arquivos atualizados:

    npm run build
    
### Copiar os arquivos de build para Capacitor:
Após a construção, você precisa copiar os novos arquivos de build para o diretório do Capacitor:

    npx cap copy android
    
### Sincronizar as alterações no Android Studio:
Se as alterações ainda não aparecem, você pode tentar sincronizar o projeto no Android Studio:

Abra o Android Studio.
No menu superior, clique em File > Sync Project with Gradle Files.

### Verificar as Dependências do Capacitor:
Certifique-se de que as dependências do Capacitor estejam atualizadas. Você pode fazer isso executando o comando de sincronização do Capacitor:

    npx cap sync android
    
