<footer>
    <div>
        <i class="facebook"/>
        <i class="pinterest"/>
        <i class="instagram"/>
    </div>
</footer>
  
<style scoped>
    footer {
        background-image: url('../assets/images/pattern-hills.svg');
        background-size: cover;
        background-position-x: left;
        height: 25%;
        position: absolute;
        bottom: 0;
        width: 100%;

        --bg-image-facebook: url('../assets/images/icon-facebook.svg');
        --bg-image-facebook-hover: url('../assets/images/icon-facebook-hover.svg');
        --bg-image-instagram: url('../assets/images/icon-instagram.svg');
        --bg-image-instagram-hover: url('../assets/images/icon-instagram-hover.svg');
        --bg-image-pinterest: url('../assets/images/icon-pinterest.svg');
        --bg-image-pinterest-hover: url('../assets/images/icon-pinterest-hover.svg');
    }

    div {
        margin: 0 auto;
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        margin-top: 120px;
        max-width: 180px;
    }

    i {
        width: 30px;
        height: 30px;
        background-size: cover;
        display: inline-block;
        cursor: pointer;
    }

    i.facebook {
        background-image: var(--bg-image-facebook);
    }
    i.facebook:hover {
        background-image: var(--bg-image-facebook-hover);
    }
    i.instagram {
        background-image: var(--bg-image-instagram);
    }
    i.instagram:hover {
        background-image: var(--bg-image-instagram-hover);
    }
    i.pinterest {
        background-image: var(--bg-image-pinterest);
    }
    i.pinterest:hover {
        background-image: var(--bg-image-pinterest-hover);
    }

    @media (max-width: 564px) {
        footer {
            background-position-x: -280px;
        }

        div {
            margin-top: 160px;
            max-width: 200px;
        }

        i {
            width: 38px;
            height: 38px;
        }
    }
  </style>