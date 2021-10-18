<h1>Retorno void</h1>
<hr>
<p>
O que é esse retorno Void?

é quando uma função recebe os parâmetros que foram enviados, mas ela nã otem nenhum tipo de retorno, ou seja, não esperamos isso.

Exemplo, como remover algo da tela
</p>

```function removerElemento(el: HTMLElement): void {
    //Processo de remoção do eleento.
    el.remove()
}

removerElemento(document.getElementById('teste'))

<hr>

<p>
⇒ Caso a gente não especifique que quer um retorno para o void, ele mesmo, com sua inteligência, fará isso.

⇒ Como especificamos o **:void** não podemos mandar um retorno para ele fazer, exemplo:
</p>

```function removerElemento(el: HTMLElement): void{
    //Processo de remoção do eleento.
    el.remove()

    return 'Ola mundo'
    //<>ERRO<>
    //Type 'string' is not assignable to type 'void'.ts(2322)
}

removerElemento(document.getElementById('teste'))

<hr>

<p>Usamos o void quand queremos parar uma execução de função ou código</p>

```function removerElemento(el: HTMLElement): void{
    //Processo de remoção do eleento.
    
    if(el.classList) {
        return
    }
    el.remove()

}

removerElemento(document.getElementById('teste'))

<hr>

<p>Nesse caso ele faz um verificação e remove o eleemento, mas não retorna nada. Tanto é que se passarmo algum valor para ser retonado ele dar o seguinte erro:</p>

<hr>

```Erro => Type 'string' is not assignable to type 'void'.ts
Código =>

function removerElemento(el: HTMLElement): void{
    //Processo de remoção do eleento.
    
    if(el.classList) {
        return "blba"
    }
    el.remove()

}

removerElemento(document.getElementById('teste'))

<hr>

<h2>resumo:</h2>

<p>Seu eu não por o **void** e não retornar nada, toda a função assume o **void.** Caso eu faça um retorno ele vai entender que o retorno é uma string ou o que for retornado.
</p>

<h6>Em que momento fazer isso</h6>

```function algo(): void {
    return true
}

=> isso ainda não é permitido, mas existe algumas
situaçãoes em que vão.
Quando temos um type de função com retorno void

<hr>

```type QualquerFunção = () => void;

const algo:QualquerFunção = () => {
    return 'ola'
}

algo()
ou
let return = algo()
=> posso retorn qualquer coisa, mas o TS, vai ignorar.
Não importa se vai ou não vir algo. Se vir tudo bem, se não, tudo bem também, não estou esperando nada disso.
!!!!!! => Ao CONTRÁRIO  de qunado uma função é criado com o RETORNO VOID

Dessa menira, ele não apresenta nenhum erro, aceita
normalmente.
Exite um motivo para isso.

<p>
Quando criamos um type é algo generalizado não estamos determinando que qualquer função que usa-lo vai ter retorno void, mas sim que todo mundo que usar aquele tipo ali, não vai esperar nennhum tipo de retorno.

⇒ Quado criamos um retorno no type, não estamos esperando por isso
</p>