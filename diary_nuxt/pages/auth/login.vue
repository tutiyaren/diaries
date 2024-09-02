<template>
  <div class="container">

    <h2 class="title">ログイン</h2>

    <form method="" action="" class="form">
      <div class="form-email">
        <label for="email" class="form-email__title">メールアドレス</label>
        <input type="email" id="email" class="form-email__input" name="email" placeholder="test@example.com">
      </div>
      <div class="form-password">
        <label for="password" class="form-password__title">パスワード</label>
        <input type="password" id="password" class="form-password__input" name="password">
      </div>
      <div class="form-button">
        <button type="submit" class="form-button__submit">ログインする</button>
      </div>
    </form>

    <p class="move">
      <n-link to='./register' class="move-register">会員登録がまだの方はこちら</n-link>
      <n-link to='./emailInput' class="move-password">パスワードを忘れた方はこちら</n-link>
    </p>

  </div>
</template>

<script>

</script>


<style scoped>
.title {
  font-size: clamp(1.4rem, 3vw + 1rem, 2.5rem);
  letter-spacing: 10px;
  margin-top: 0;
  padding-top: 8%;
  text-align:center;
}
.form {
  margin: 5% auto 8%;
  text-align: center;
  width: 100%;
}
.form-email,
.form-password {
  display: flex;
  flex-direction: column;
  margin: 4% 0 3%;
}
.form-email__title,
.form-password__title {
  cursor: pointer;
  font-size: clamp(1.2rem, 2.2vw + 0.6rem, 1.8rem);
  margin: 0 auto;
  text-align: left;
  width: 60%;
}
.form-email__input,
.form-password__input {
  background-color: #c5fff3;
  border: none;
  border-bottom: 1px dashed #80a49d;;
  color: #4e4e4e;
  font-size: clamp(1rem, 2vw + 0.5rem, 1.6rem);
  margin: 0 auto;
  outline: none;
  padding: 1% 1%;
  width: 55%;
}
.form-button {
  margin-top: 8%;
}
.form-button__submit {
  background-color: #8df7d8;
  border: none;
  border-radius: 5px;
  box-shadow: 3px 3px 4px #4e8776;
  color: #4e4e4e;
  cursor: pointer;
  font-size: clamp(0.9rem, 1.8vw + 0.4rem, 1.5rem);
  padding: 1% 2%;
}
.form-button__submit:hover {
      background-color: #27fcbc;
}
.move {
  align-items: center;
  display: flex;
  font-size: clamp(0.7rem, 1.7vw + 0.2rem, 1.2rem);
  justify-content: space-around;
  text-align: center;
}
.move-password,
.move-register {
  text-decoration: none;
  opacity: 0.7;
}
.move-password:hover,
.move-register:hover {
  opacity: 1;
}

@media screen and (max-width: 528px) {
  .title {
    letter-spacing: 3px;
    padding-top: 12%;
  }
  .form {
    margin: 10% auto 12%;
  }
  .form-emaill,
  .form-password {
    margin: 4% 0 8%;
  }
  .form-email__title,
  .form-password__title {
    width: 80%;
  }
  .form-email__input,
  .form-password__input {
    width: 75%;
  }
  .form-button {
    margin-top: 10%;
  }
  .move {
    flex-direction: column-reverse;
  }
  .move-register {
    margin-bottom: 8%;
  }
}

</style>
