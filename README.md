Webassembly
O que é Single Page Application
flutter create aula_flutter_web --platforms=web
Mostrar a Estrutura do Projeto
	
Stateless x Stateful
Rotas Nomeadas
Navegação e Passagem de Parâmetros
MouseRegion
Retirar # das rotas
	setPathUrlStrategy()
flutter run -d chrome
GoRouter
Shared Preferences
Completers
	https://api.flutter.dev/flutter/dart-async/Completer-class.html
Guards
MediaQuery.of(context).size
flutter build web
Publicaçao
Firebase Hosting

firebase login:add
firebase init
firebase deploy

___________________________________________________________________________________________________________________________________________
##🚀 Flutter Web & Conceitos Essenciais
Este repositório contém anotações e práticas sobre o desenvolvimento com Flutter, focando em performance (WASM), navegação e estrutura de widgets.
___________________________________________________________________________________________________________________________________________
##🌐 Flutter Web & WebAssembly (WASM)
O Flutter Web evoluiu para suportar WASM, mudando a forma como o navegador processa o código.O que é WASM? 
É uma linguagem de baixo nível que os navegadores modernos entendem.
Performance: Diferente do JS, que precisa ser interpretado e convertido em bytecode (1100), o WebAssembly entrega o bytecode diretamente.
Ganho: Pode ser até 3x mais rápido que o Flutter compilado apenas com JavaScript puro.Uso Ideal: Flutter Web é excelente para SPA (Single Page Applications), onde o conteúdo é carregado de uma vez, similar ao React e Angular.
___________________________________________________________________________________________________________________________________________
##🛠️ Comandos Úteis (CLI)Comando
Descriçãoflutter doctorVerifica a "saúde" da instalação e dependências no PC.
flutter create nome_projeto
Cria um projeto para todas as plataformas disponíveis.
flutter create . --platforms=android
Adiciona suporte a uma nova plataforma em um projeto já existente.
flutter create nome --platforms=web
Cria um projeto focado apenas em uma plataforma específica.
💡 Dica Extra: Use -h no final dos comandos (ex: flutter create -h) para ver todas as opções de customização disponíveis.
___________________________________________________________________________________________________________________________________________
##🏗️ Widgets & Estados
No Flutter, tudo é um Widget. A principal diferença reside na gestão de estado:
StatelessWidget vs StatefulWidgetStatelessWidget: Possui apenas uma classe. Ideal para componentes estáticos.
StatefulWidget: Possui duas classes. Permite o uso do método setState() para atualizar a interface quando os dados mudam.
💡 Dica de Organização: Geralmente usamos Stateless para componentes menores e Stateful para páginas que controlam dados dinâmicos.
A Estrutura Básica (Scaffold)O Scaffold é o widget que dá a "sensação de página", oferecendo suporte para appBar, body, e drawer.DartWidget build(BuildContext context) {
  return Scaffold(
    appBar: AppBar(title: Text('Home Page')),
    body: Center(child: Text('Olá, Flutter!')),
  );
}
___________________________________________________________________________________________________________________________________________
##🧭 Navegação e Rotas
A navegação nativa do Flutter funciona com o conceito de Pilha (Stack):
Push: Empilha uma nova página sobre a atual.
Pop: Remove a página do topo e volta para a anterior.
Formas de Navegar:Navegação Direta: Navigator.push(...)Rotas Nomeadas: Definidas no initialRoute e chamadas via Navigator.pushNamed(...).📦 GoRouter (Recomendado para Web)Para projetos mais complexos ou que exigem parâmetros na URL (muito comum na web), utilizamos a biblioteca go_router.Vantagem: Permite passar parâmetros extras e dá uma sensação de navegação web mais fluida.Exemplo: context.go('/detalhes', extra: contador);
___________________________________________________________________________________________________________________________________________

##📌 Observações de Aprendizado
Hot Reload: Salve o código e veja a mudança instantaneamente. É o superpoder do desenvolvedor Flutter!
Arquitetura: O Flutter por padrão não impõe uma arquitetura. Você é livre para escolher (MVC, MVVM, Clean, etc).
Filhos (Child vs Children): Alguns widgets aceitam apenas um filho (child), outros aceitam múltiplos (children), conhecidos como multivalores.
