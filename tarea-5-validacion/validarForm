window.onload=function(){
  var formulario = document.forms[0];
  //agregar manejador de evento para el formulario
  if(document.addEventListener){
    formulario.addEventListener("submit", validarFormulario);
  }
  else if(document.attachEvent){
    formulario.attachEvent("onsubmit", validarFormulario);
  }
}

function validarFormulario(event){
  var inputEmail = document.getElementById('email');
  function validarFormulario(event){
    var inputfactua = document.getElementById('factura');
  //validar código de cliente

  if( !(/^\d{3}-\d{3} $/.test(valor)) ) {
    return false;
  }
  //validar correo electrónico
  if(!validarEmail(inputEmail.value)){
    console.log("email no valido");
    event.preventDefault();//evitar que formulario se envie
    return false;//dirección de correo no válida
  }

  //validar número de factura
  //formato es digito-3digitos

  if( !validarfactuara(inputfactua.value))(/^\d{3} $/.test(valor)) {
    return false;
  }


  //validar monto a pagar, solo aceptar valores en coma flotate,
  //por ejemplo: 133.30 o 1020.15

  if( !(/^\d{3}-\d{2}-\d{4}-\d{2} $/.test(valor)) ) {
    return false;
  }
  //validar tarjeta de crédito
  //formato valido es 3333-3333-3333-33333
  //16 digitos en grupos de 4 separados por guión

  if( !(/^\d{4}-\d{4}-\d{4}-\d{4}$/.test(valor)) ) {
    return false;
  }

  //validar nombre tarjeta habiente, no debe ser vacío
  var tarjetaHabiente = document.getElementById("tarjetahabiente");
  if(tarjetaHabiente.value.trim().length==0){
    console.log("tarjeta habiente no puede ser vacío");
    event.preventDefault();
    return false;
  }

  //validar fecha de experición de tarjeta
  //formato es mm-aa (dos digitos para mes, guión, dos digitos para año)
  //por ejemplo: 09-18
  var ano = document.getElementById("ano").value;
  var mes = document.getElementById("mes").value;
  var dia = document.getElementById("dia").value;

  valor = new Date(ano, mes, dia);

  if( !isNaN(valor) ) {
    return false;
  }
  //Si todo fue validado, retornar true
  console.log("ok");
  return true;
}
function getTarget(e){
  var target;
  if(e.target)
    target = e.target;
  else if(e.srcElement)
    target = e.srcElement;
  if(target.nodeType==3) //safari
    target = target.parentNode;

  return target;
}
function validarEmail(email){
  //expresión regular para validar correo
  var re = /[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+(?:[A-Z]{2}|com|org|net|gov|mil|biz|info|mobi|name|aero|jobs|museum)\b/;
  return re.test(email);
}
