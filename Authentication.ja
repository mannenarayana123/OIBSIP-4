const form = document.querySelector('#form');
const Name = document.querySelector('#Name');
const Email = document.querySelector('#Email');
const Pnumber = document.querySelector('#Pnumber');
const Password = document.querySelector('#Password');

form.addEventListener('submit',(e)=>{
    if(!validateInputs()){
    e.preventDefault()
    }
})

function validateInputs(){
    const NameVal = Name.value.trim();
    const EmailVal = Email.value.trim();
    const PnumberVal = Pnumber.value.trim();
    const PasswordVal = Password.value.trim();
    let success = true

    if(NameVal===''){
        success=false;
        setError(Name,'Name is required')
    }
    else{
        setSuccess(Name)
    }

    if(EmailVal===''){
        success = false;
        setError(Email,'Email is required')
    }
    else if(!validateEmail(EmailVal)){
        success = false;
        setError(Email,'Please enter a valid email')
    }
    else{
        setSuccess(Email)
    }

    if(PasswordVal === ''){
        success= false;
        setError(Password,'Password is required')
    }
    else if(PasswordVal.length<8){
        success = false;
        setError(Password,'Password must be atleast 8 characters long')
    }
    else{
        setSuccess(Password)
    }

    if(PnumberVal.length == 0){
        success = false;
        setError(Pnumber,'Enter the Pnumber')
    }
    else if(PnumberVal.length<10 || PnumberVal.length>10){
        success = false;
        setError(Pnumber,'Enter the 10-digit number')
    }
    else{
        setSuccess(Pnumber)
    }

    return success;

}

function setError(element,message){
    const inputField = element.parentElement;
    const errorElement = inputField.querySelector('.error')
    

    errorElement.innerText = message;
    inputField.classList.add('error')
    inputField.classList.remove('success')
}
function setSuccess(element){
    const inputField = element.parentElement;
    const errorElement = inputField.querySelector('.error')
    

    errorElement.innerText = '';
    inputField.classList.add('success')
    inputField.classList.remove('error')
}

const validateEmail = (Email)=>{
    return String(Email)
    .toLowerCase()
    .match(
        /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
    );
};