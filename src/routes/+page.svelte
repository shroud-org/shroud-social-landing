<script>
    import { Quote } from "@lucide/svelte";
</script>

<div class="content">
    <div class="newsletter">
        <h1>We're building the next generation of group communication.</h1>
        <h3>Subscribe to the newsletter for updates:</h3>
        <form action="https://buttondown.com/api/emails/embed-subscribe/shroudsocial"
                method="post"
                class="embeddable-buttondown-form" >
            <label for="bd-email">Enter your email:</label>
            <input type="email" name="email" id="bd-email" />
            <input type="submit" value="Subscribe" />
            <p>
                <a href="https://buttondown.com/refer/shroudsocial" target="_blank">
                    Powered by Buttondown.
                </a>
            </p>
        </form>
    </div>
</div>

<style>
    .content {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 25px;
    }

    .newsletter {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background: radial-gradient(circle at 50% 20%, rgb(222 255 255 / 0.11) 0%, rgb(222 255 255 / 0.11) 100%);
        width: 100%;
        padding: 50px;
        backdrop-filter: blur(50px);
        border: 1px solid rgba(255, 255, 255, 0.1);
    }

    h1, h3, form {
        text-align: center;
    }
</style>