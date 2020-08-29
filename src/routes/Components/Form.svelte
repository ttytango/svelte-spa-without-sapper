<script>
import Login from './Login.svelte';
    function openPopUpAddition() {
        var x = Number(addOne.value);
        var y = Number(addTwo.value);
        var result = x + y;
        alert(result);
    }    
    function openPopUpSubtract() {
        var x = Number(addOne.value);
        var y = Number(addTwo.value);
        var result = x - y;
        alert(result);
    }
    function OpenPopUpName() {
        var name = { "firstname": myFirstName.value, "secondname": mySecondName.value };
        alert("Hello there " + name.firstname + " " + name.secondname + "!");
    }
    function OpenPopUpMultiply() {
        var x = myNum.value;
        var y = myNumTwo.value;
        var result = x * y;
        alert(result);
    }
</script>

<style>

.grid {
    margin-top: 2rem;
    background: linear-gradient(to right bottom, #488169a4, rgba(51, 238, 51, 0.438));
    padding-top: 1em;
    padding-bottom: 1em;
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 3fr));
    grid-template-rows: 4fr;
    gap: 2px;
    grid-template-areas: inherit;  
    box-shadow: 2px 2px 8px grey;  
}
.inner-left,
.inner-right {
    padding: 1em;
    display: block;
    text-align: center;
    border-radius: 6px;
    margin-left: 1rem;
    margin-right: 1rem;
}
/* .inner-left:hover,
.inner-right:hover {
    box-shadow: -1px 2px 2px black;
    filter: hue-rotate(-25deg);
    transition: all 6s;
} */
.inner-left {
    background: rgba(140, 127, 140, 0.678);
    box-shadow: inset -2px 1px 3px #585885b0;
    
}
.inner-right {
    background: rgba(179, 219, 179, 0.678);
    box-shadow: inset 2px 1px 3px #8989afbb;
}
.inner {
    top: 50%;
    left: 50%;
    margin-left: 1rem;
    margin-right: 1rem;
    text-align: center;
    background: rgba(209, 208, 208, 0.678);
    padding: 1em;
    border-radius: 4px;
    box-shadow: 1px 1px 8px grey;
}
.inner:hover {
    box-shadow: 1px 2px 10px black;
}
input {
    background: rgba(229, 180, 191, 0.9);
    font-size: 1.2rem;
    border-radius: 4px;
    /* color: #0000; */ 
}
input:active, input:focus {
    background: rgb(255, 255, 255);
    /* color: #0000; */
}

button {
    background: rgba(255, 255, 255, 1);
    outline-style: none;
    border-radius: 8px;
    cursor: pointer;
    margin-top: 0.5rem;
}
#addbtn {
    background: #3e3;
}
#addbtn:active {
    background: rgb(22, 110, 22);
}
#subbtn {
    background: rgb(230, 191, 85);
}
#subbtn:active {
    background: rgb(124, 103, 46);
}
</style>
<div class="grid">
    <div class="inner-left">        
        <form id="additionForm">
            <label name="num">
                <input id="addOne" type="number" name="num" value="" placeholder="0" />
            </label>
            <label name="num2">
                <input id="addTwo" type="number" name="num2" value="" placeholder="0" />
            </label>
            <button type="Button" id="addbtn" on:click={openPopUpAddition}>Add!</button>
            <button type="Button" id="subbtn" on:click={openPopUpSubtract}>Subtract!</button>
        </form>
    </div>
        <div class="inner">
            <form id="myForm">
                <label name="firstname">
                    <input id="myFirstName" name="firstname" value="" placeholder="Enter your first name" />
                </label>        
                <label name="secondname">
                    <input id="mySecondName" name="secondname" value="" placeholder="Enter your second name" />
                </label>
                <button type="Button" on:click={OpenPopUpName}>Greetings!</button>
            </form>
        </div>
    <div class="inner-right">
        <form id="multiplicationForm">
            <label name="num">
                <input id="myNum" type="number" name="num" value="" placeholder="0" />
            </label>
            <label name="num2">
                <input id="myNumTwo" type="number" name="num2" value="" placeholder="0" />
            </label>
            <button type="Button" on:click={OpenPopUpMultiply}>Multiply!</button>
        </form>
    </div>


</div>
