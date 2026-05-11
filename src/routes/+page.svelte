<script>
    import { Quote } from "@lucide/svelte";
</script>

<div class="container">
    <div class="hero">
        <div>
            <h1>shroud.social is coming soon.</h1>
            <h2>A new home for your community.</h2>
        </div>
        <form
                action="https://buttondown.com/api/emails/embed-subscribe/shroudsocial"
                method="post"
                class="embeddable-buttondown-form"
        >
            <h3>Sign up for the newsletter:</h3>
            <input type="email" name="email" id="bd-email" placeholder="Enter your email" />
            <input type="submit" value="Subscribe" />
            <p>
                <a href="https://buttondown.com/refer/shroudsocial" target="_blank" class="buttondown-link">
                    Powered by Buttondown.
                </a>
            </p>
        </form>
    </div>
    <div class="content">
        <div class="section" id="who">
            <h1>Who?</h1>
            <p>shroud.labs is an upcoming social enterprise dedicated to building open source, decentralized and privacy-optimised services.</p>
            <p>All code is and will be 100% human written.</p>
        </div>
        <div class="section" id="what">
            <h1>What?</h1>
            <p>shroud.social is a decentralized and private alternative to existing community messaging services.</p>
        </div>
        <div class="section" id="where">
            <h1>Where?</h1>
            <p>shroud.social is a federated service, which means instead of being forced to trust one company with your data, you have the option to keep it to yourself or a company you trust, whilst still having access to your communities.</p>
            <p>A flagship instance will be run by us, anyone else is welcome to run their own instance for themselves, their friends, for anyone.</p>
        </div>
        <div class="section" id="when">
            <h1>When?</h1>
            <p>shroud.social is currently in development, there is no current planned release date but you can sign up for our <a href="https://buttondown.com/shroudsocial">newsletter</a> for news updates.</p>
        </div>
        <div class="section" id="why">
            <h1>Why?</h1>
            <p>The internet should be free, open, decentralized and private. So far, we have been failed. Large corporations run too many services which are required for most people. We want to change that, starting with shroud.social</p>
            <p>Read the shroud.labs mission statement <a href="https://buttondown.com/shroudsocial/archive/shroudlabs-mission-statement/">here</a></p>
        </div>
    </div>
</div>

<style>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .hero {
        height: 100vh;
        display: flex;
        flex-direction: column;
        gap: 64px;
        justify-content: center;
    }

    .hero h1 {
        font-size: 64px;
        font-family: 'ZT Nature', sans-serif;
        font-style: normal;
    }

    .content {
        display: flex;
        flex-direction: column;
        align-items: center;
        flex: 1;
        width: 100%;
        background: rgb(255 255 255 / 0.7);
        color: #000000;
        gap: 20px;
        box-sizing: border-box;
        padding: 50px;
    }

    .section {
        display: flex;
        flex-direction: column;
        justify-content: left;
        width: 70vh;
    }

    input[type="email"] {
        padding: 12px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        border-radius: 25px;
        box-sizing: border-box;
    }

    input[type=submit] {
        background-color: #4CAF50;
        color: white;
        padding: 14px;
        margin: 8px 0;
        border: none;
        border-radius: 25px;
        cursor: pointer;
    }

    input[type=submit]:hover {
        background-color: #45a049;
    }

    a.buttondown-link {
        text-decoration: none;
        color: rgb(255 255 255 / 0.4);
    }
</style>