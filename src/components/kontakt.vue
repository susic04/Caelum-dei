<script setup>
    import { ref, onMounted } from 'vue'
    import logo from '../assets/logo.png'
    
</script>

 <template>
    <div id="kontakt" class="kontakt">
        <div class="container">
            <div class="kontakt-forma">
                <div class="logo-container">
                    <img
                    :src="logo"
                    alt="Caelum Dei logo"
                    class="logo"
                    />
                    <div class="o-nama">
                        <p class="tekst">
                            Za narudžbe i upite, slobodno nas kontaktirajte putem e-maila ili instagrama.<br>
                            Radujemo se vašem javljanju i prilici da vam pomognemo pronaći savršen duhovni dodatak!
                        </p>
                        <a
                            href="https://www.instagram.com/the_zoric_/"
                            target="_blank"
                            rel="noopener"
                            >
                            <i class="fa-brands fa-instagram"></i>
                        </a>
                        <a
                            href="https://mail.google.com/mail/?view=cm&fs=1&to=ivansusic6@gmail.com"
                            target="_blank"
                            rel="noopener"
                            >
                            <i class="fa-solid fa-envelope"></i>
                        </a>
                    </div>
                </div>
            </div>
        </div>
        <div class="footer">
            <hr></hr>
            <p class="tekst">© 2024 Caelum Dei.</p>
        </div>
    </div>
 </template>

 <style scoped>
    .kontakt {
        height: 100vh;
        width: 100vw;
        background: linear-gradient(135deg, #f5f7fa 0%, #e8eef5 50%, #d4dce8 100%);
        display: flex;
        flex-direction: column;
    }
    .container {
        height: 100%;
        width: 75vw;
        display: flex;
        justify-content: center;
        flex: 1;
    }
    .kontakt-forma {
        height: 80%;
        width: 80%;
        text-align: center;
    }
    .logo {
        height: 300px;
        width: auto;
    }
    .tekst{
        font-size: 1.1rem;
        font-family: 'Georgia', serif;
        line-height: 1.8;
        color: #555;
    }

    i {
        font-size: 24px;
        color: #2c3e50;
        cursor: pointer;
    }

    i:hover {
        color: #e1306c; /* instagram pink */
    }
    i{
        margin-right: 5px;
        margin-left: 5px;
        margin-top: 10px;
    }

    hr {
        width: 60%;
        border: none;
        border-top: 1px solid #bbb;
    }
    .footer {
        width: 100vw;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 1.5rem 0; /* 👈 ravnomjeran razmak gore i dole */
        gap: 1rem;        /* 👈 jednak razmak između hr i teksta */
    }
 </style>