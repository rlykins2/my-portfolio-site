<script lang="ts">

    let about: Boolean = false;
    let contact: Boolean = false;
    const activate_about = () => {about = true};
    const cancel_about = () => { about = false};

    const activate_contact = () => {contact = true};
    const cancel_contact   = () => {contact = false};

</script>

<div class="flex-container">
<div class="first-name">BO</div>
<h1 class="last-name">lykins</h1>
</div>
<nav class="nav-bar">
<ul class="navigation-list">
    <li>
    <a href="" class="navigation-list__link" on:click={activate_about}>
    About
    </a>
    </li>
     <li>
     <a href="" class="navigation-list__link" on:click={activate_contact}>
        Contact me
     </a>
     </li>
   </ul>
 </nav>
 <div class="projects-section">
 <h1>Projects</h1>
 <div class="project-links">
    <div class="project-link">
    <div class="project-info">
            <img src="images/frontendmentor.png" alt="">
            <div class="project-title">Frontendmentor Collection</div>
            <div class="project-description">Projects from frontendmentor</div>
    </div>
    </div>
    <div class="project-link">
        <div class="project-info secondary">
            <div class="project-title">Real Analysis in Coq</div>
            <div class="project-description">Tao's Analysis 1 in Coq Rules</div>
        </div>
    </div>
 </div>
</div>

<div class="about-page {about ? "" : "inactive"}" on:click={cancel_about}>
    <div class="about__popup" on:click|stopPropagation>
        <div class="about__avatar">
            <img src="" alt="">
        </div>
        <h1 class="about__header">About me</h1>
        <p class="about__text">
            Hello, my name is Robert Lykins or Bo. I am a 28 year old computer science major currently pursuing a master's degree at the university of Arizona. My interests include: web development, artificial intelligence, and formal software verification. 
        </p>
</div>
</div>


<div class="contact-page {contact ? "" : "inactive"}" on:click={cancel_contact}>
    <div class="contact__popup" on:click|stopPropagation>
        <h1 class="about__header">Contact Me</h1>
        <label for="">
            Your Name
            <input type="text" name="" id="" class="contact__input"></label>
        <label for="">
            Your Email
            <input type="text" name="" id="" class="contact__input"></label>
        <label for="">
            Message <br>
            <textarea class="contact__message-input"></textarea></label>


    <button class="submit">Submit</button>
</div>
</div>

<style>


:global(body)
{
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: var(--color-background);
    position: relative;
    flex-direction: column;
}

.nav-bar{
}
.flex-container{
   display: flex;
   flex-direction: column; 
   height: 90vh;
   align-items: center;
   justify-content: center;
}

.navigation-list{
    list-style: none;
    display: flex;
    gap: 1rem;
}

.navigation-list__link{
    font-size: 2rem;
    text-decoration: none;
    color: var(--color-accent);
}


.about-circle{

}

.first-name{
    color: var(--color-text);
    font-weight: 700;
    font-size: 20ch;
    border-radius: 50%;
    text-align: center;
    user-select: none;
}


.o{
    color: var(--color-text);
    font-weight: 700;
    font-size: 20ch;
    cursor: pointer;
}


.last-name{ 
    font-weight: 400;
    font-size: 10ch;   
    text-transform: uppercase;     
}


.projects-section{
    background-color: var(--color-heading);
    width: 100%;
    height: auto;
    text-align: center;
}

.projects-section > h1{
    font-size: 7ch;
    color: var(--color-background);
}


.project-links{
    padding: 2rem;
    display: flex;
    gap: 1rem;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
}

.project-link
{
    min-width: 30rem;
    min-height: 15rem;
    background-color: var(--color-text);
    border-radius: 5px;
    border: 1px solid var(--color-border);
    cursor:pointer;
    position: relative;
    overflow: hidden;
}

.project-info
{

    position: absolute;
    width: 100%;
    bottom: 0;
    background-color: var(--color-accent);
}

.project-info > img{
    max-width: 100%;
    max-height: 100%;
    object-fit: cover;
    display: block; 
    border-radius: 5px 5px 0 0;
}

.project-title{
    font-size: 2rem;
    font-weight: 700;
    color: var(--color-surface);
}
.project-title.secondary{
}

.project-description{
    font-size: 1.5rem;
    font-weight: 400;
    color: var(--color-surface);
}

.project-description.secondary{
    background-color: #E31837;
}

.about-page, .contact-page{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,0.2);
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
}

.about-page.inactive{
    display: none;
}

.contact-page.inactive{
    display:none;
}

.about__popup, .contact__popup{
    position: relative;
    background-color: var(--color-background);
    border-radius: 7px;
    padding: 3rem;
    cursor: initial;
}


.about__header{
    text-align: center;
    font-size: 4rem;
    font-weight: 700;
}

.about__avatar{
    margin-right: auto;
    margin-left: auto;
    width: 12rem;
    height: 12rem;
    background-color: var(--color-text);
    border-radius: 50%;
}

.about-popup::after{
    content: '';
    position: absolute;
    top: 0;
    background-color: #E31837; 
    width: 10rem;
    height: 10rem;
}

.about__text{
    max-width: 50ch;
    color: var(--color-text);
}

.about__header{
    color: var(--color-heading);
}

.contact__popup{
    display: flex;
    flex-direction: column;
    gap: 1rem;
}

.contact__input{
    width: 100%;
    padding: 1rem;

}

.contact__message-input{
    resize: none;
    width: 100%;
    height: 100px;
}

.submit{
    flex-grow: 0;
    flex-shrink: 0;
    font-size: 1.2rem;
    border-radius: 5px;
    cursor: pointer;
    border: 1px solid var(--color-border);
    color: var(--color-background);
    align-self: flex-end;
    padding: 1rem;
    background-color: var(--color-secondary);
}

</style>

