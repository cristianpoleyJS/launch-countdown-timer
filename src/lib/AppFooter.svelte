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

    @media (max-width: 992px) {
        footer {
            background-position-x: -280px;
        }

        div {
            max-width: 200px;
            margin-top: 80px;
        }

        i {
            width: 38px;
            height: 38px;
        }
    }
  </style>