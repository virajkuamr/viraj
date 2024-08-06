document.addEventListener('DOMContentLoaded', () => {
    const form = document.getElementById('contact_form')
    form.addEventListener('submit', (event) => {
        event.preventDefault();
        const fname = document.getElementById("First Name").value;
        const lname = document.getElementById("Last Name").value;
        const phone = document.getElementById("Phone").value;
        const email = document.getElementById("Email ID").value;
        const date = document.getElementById("date").value;
        const message = document.getElementById("Message").value;

        const boolean = validate(fname,lname,phone,email,message);

        if(boolean){
            form.submit();
        }

    });
    function validate(fname,lname,phone,email,message) {


        if (fname.length < 5) {
            alert("Please Enter a valid name");
            return false;
        }
        if (lname.length < 5) {
            alert("Please Enter a valid name");
            return false;
        }
        if (email.indexOf("@") == -1 || email.length < 6) {
            alert("Please Enter a valid Email");
            return false;
        }
        if (isNaN(phone) || phone.length != 10) {
            alert("Please Enter a valid Phone number");
            return false;
        }
        if (message.length <= 50) {
            alert("The message length should be greater than 50");
            return false;
        }
        alert("Form Submitted Succesfully!");
        return true;
    }
});

