Criei um função genérica para efetuar o focus sem ficar repetindo código.
Este exemplo é para o alert do bootbox, para os outros (confirm, etc…) é só adaptar o código:

//HTML
<form>
    <h3>Exemplo Bootbox com focus</h3>
    <input type="text" id="nome" name="nome" placeholder="nome"/>
    <input type="text" id="sobrenome" name="sobrenome" placeholder="sobrenome"/>

    <button type="button" id="btnAlerta">Alert Bootbox</button>
</form>




//JQUERY
<script>
$(function(){ 
    $('#btnAlerta').on('click',function(){
        const snome = $('#nome').val();
        const ssobrenome = $('#sobrenome').val();
        const mensagem = 'Seu nome é:\n '+snome+' '+ssobrenome+'';
        falert('título do modal',mensagem,'#sobrenome');
     });
});

//JAVASCRIPT
function falert(tit,msg,obj){
    const box = bootbox.alert({
        size: 'small',
        title: tit,
        message:'<p class="text-danger" style="margin:3%;padding:3%;">'+msg+'</p>'
    });
    setTimeout(function(){ 
        $('div.bootbox.modal').addClass('box');
        $('div.bootbox.modal .modal-dialog div.modal-header h4.modal-title').addClass('titulo');
        $('div.bootbox.modal .modal-dialog div.modal-footer button').addClass('botao').text('Fechar');
     },100);
    $('div.bootbox.modal .modal-dialog div.modal-header button').addClass('fechar');
    box.on('hidden.bs.modal',function(){ $(obj).focus(); });
}
</script>


Segue o exemplo na prática

https://jsfiddle.net/marsites/tLwo253e/14/
