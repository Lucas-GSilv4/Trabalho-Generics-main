Alterações no código: 
- O depósito de eletrônicos agora é declarado como Deposito<Eletronico>, no lugar do raw type Deposito.
  Antes, o compilador aceitava qualquer objeto no depósito.
- Foi criado um novo depósito para guardar a maçã.
- Removidos os casts (Eletronico) em obterItem(0) e obterItem(2). Eles eram incorretos porque o método retorna Optional<T>,
  e não o item diretamente.
- O índice válido (obterItem(0)) agora é tratado com ifPresent(), que imprime o item somente se ele existir.
- O índice invalido (obterItem(2)) foi tratado usando orElseThrow(), que lança uma IllegalArgumentException caso não exista um
  item nessa posição da lista. O orElseThrow também foi envolvido em um try/catch para evitar que o programa
  encerre de forma abrupta.
