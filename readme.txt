English version
====================

Create a generic function to focus without repeating the code.

This example is for the bootbox alert, for others (confirm, etc ...) just adapt the code:

    <script>
    $(function(){
    	$('#btnAlerta').on('click',function(){
    		falert('modal title','message you want to view','#nome');
    	});
    });
    function falert(tit,msg,obj){
        var box = bootbox.alert({
            size: 'small',
            title: tit,
            message:'<p>'+msg+'</p>'
        });
        box.on('hidden.bs.modal',function(){
            $(obj).focus();
        });
    }
    </script>

    <input type="text" id="nome" name="nome" />
    <button type="button" id="btnAlerta">Alert</button>


follows the example in practice
https://jsfiddle.net/marsites/tLwo253e/

====================
Versão em Português
====================
Criei um função genérica para efetuar o focus sem ficar repetindo código.

Este exemplo é para o alert do bootbox, para os outros (confirm, etc...) é só adaptar o código:

<script>
$(function(){
	$('#btnAlerta').on('click',function(){
		falert('título do modal','mensagem que deseja exibir ','#nome');
	});
});
function falert(tit,msg,obj){
    var box = bootbox.alert({
        size: 'small',
        title: tit,
        message:'<p>'+msg+'</p>'
    });
    box.on('hidden.bs.modal',function(){
        $(obj).focus();
    });
}
</script>

<input type="text" id="nome" name="nome" />
<button type="button" id="btnAlerta">Alerta</button>


segue o exemplo na prática
https://jsfiddle.net/marsites/tLwo253e/

