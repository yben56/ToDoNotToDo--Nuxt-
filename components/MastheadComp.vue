<template>
    <div id="masthead">
        <div class="container">
            <div class="row">
                <div class="col-xs-12">
                    <div class="locale">
                        <LocaleComp />
                    </div>
                    <div class="auth">
                        <div v-if="!token">
                            <!--Login-->
                            <ModalComp template="LoginComp" :title="$t('Login')">
                                <template v-slot:body-content>
                                    <AuthLoginComp />
                                </template>
                                <template v-slot:toggle-btn>
                                    <button class="login-btn btn btn-sm btn-primary" data-bs-toggle="modal" data-bs-target="#LoginComp">
                                        <i class="fa-solid fa-right-to-bracket"></i>
                                        {{ $t('Login') }}
                                    </button>
                                </template>
                            </ModalComp>
                            <!--Signup-->
                            <ModalComp template="SignupComp" :title="$t('Signup')">
                                <template v-slot:body-content>
                                    <AuthSignupComp />
                                </template>
                                <template v-slot:toggle-btn>
                                    <button class="signup-btn btn btn-sm btn-danger" data-bs-toggle="modal" data-bs-target="#SignupComp">
                                        <i class="fa-solid fa-pencil"></i>
                                        {{ $t('Signup') }}
                                    </button>
                                </template>
                            </ModalComp>
                        </div>
                        <div v-else>
                            <img class="rounded-circle shadow-4-strong img-thumbnail" :src="profile_pic" />
                            <b class="mt-1 ms-3 me-3">{{ firstname }}</b>
                            <MenuComp/>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
const token = useCookie('token').value
const firstname = useCookie('firstname').value
const profile_pic = useCookie('profile_pic').value
</script>


<style scoped lang="scss">
#masthead {
	padding: 15px;
    background-color: #fdfdfd;
    border-bottom: solid 1px #f4f4f4;

    .container {
        position: relative;

        .locale {
            display: inline-block;
        }

        .auth {
            display: inline-block;
            float: right;
        }
    }

    .login-btn {
        margin: 0 10px;
    }

    .img-thumbnail {
        display: inline;
        width: 30px;
    }
}
</style>