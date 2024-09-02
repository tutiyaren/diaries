<template>
  <nav class="navMenu">
    <ul class="navMenu-ul">
      <li class="navMenu-ul__item">
        <n-link to="/" class="n-link">
          <i class="fa-solid fa-house"></i>
          <p class="navMenu-ul__title">ホーム</p>
        </n-link>
      </li>
      <li class="navMenu-ul__item">
        <n-link to="/create" class="n-link">
          <i class="fa-solid fa-pen"></i>
          <p class="navMenu-ul__title">新規作成</p>
        </n-link>
      </li>
      <li class="navMenu-ul__item">
        <n-link to="/profile/analysis" class="n-link">
          <i class="fa-solid fa-chart-simple"></i>
          <p class="navMenu-ul__title">分析</p>
        </n-link>
      </li>
      <li class="navMenu-ul__item">
        <n-link to="/profile/mypage" class="n-link">
          <i class="fa-solid fa-user"></i>
          <p class="navMenu-ul__title">マイページ</p>
        </n-link>
      </li>
      <li class="navMenu-ul__item">
        <button @click="openDialog" class="n-link logoutButton">
          <i class="fa-solid fa-right-to-bracket"></i>
          <p class="navMenu-ul__title">ログアウト</p>
        </button>
      </li>
    </ul>

    <dialog ref="logoutDialog" class="logout-dialog">
      <div class="dialog-inner">
        <p class="logout-message">ログアウトしますか？</p>
        <div class="dialog-buttons">
          <button @click="confirmLogout" class="dialog-buttons__yes">はい</button>
          <button @click="closeDialog" class="dialog-buttons__no">キャンセル</button>
        </div>
      </div>
    </dialog>
  </nav>
</template>

<script>
export default {
  name: 'NavMenu',
  methods: {
    openDialog() {
      this.$refs.logoutDialog.showModal();
      document.body.style.overflow = 'hidden';
    },
    closeDialog() {
      this.$refs.logoutDialog.close();
      document.body.style.overflow = '';
    },
    confirmLogout() {
      this.closeDialog();
      this.$router.push('/');
    },
  },
  mounted() {
    this.$refs.logoutDialog.addEventListener('click', (e) => {
      if (!e.target.closest('.dialog-inner')) {
        this.closeDialog();
      }
    });
  }
};
</script>

<style scoped>
.navMenu {
  background-color: #a7ffed;
  box-shadow: 4px 0 5px #bebebe;
  display: flex;
  flex-direction: column;
  height: 100vh;
  left: 0;
  padding: 5% 3%;
  position: fixed;
  top: 0;
  transition: 0.7s;
  width: 2%;
}
.navMenu:hover {
  width: 10%;
}
.navMenu-ul {
  display: flex;
  flex-direction: column;
  gap: 60px;
  list-style: none;
  margin: 0;
  padding: 0;
}
.n-link {
  align-items: center;
  display: flex;
  text-decoration: none;
  width: 100%;
}
.navMenu-ul__item {
  align-items: center;
  display: flex;
  position: relative;
}
.navMenu-ul__title {
  color: #76b7a5;
  font-size: clamp(0.5rem, 1vw + 0.5rem, 1rem);
  margin-left: 10%;
  opacity: 0;
  transition: 0.7s;
  white-space: nowrap;
}
.navMenu-ul__title:hover {
  color: #4e4e4e;
  font-weight: bold;
}
.navMenu:hover .navMenu-ul__title {
  opacity: 1;
}
.fa-solid {
  color: #76b7a5;
  font-size: clamp(0.6rem, 1vw + 0.7rem, 1.5rem);
}
.logoutButton {
  background-color: #a7ffed;
  border: none;
  cursor: pointer;
  padding-left: 0;
  width: 100%;
}
.logout-dialog::backdrop {
  background: rgba(95, 142, 133, 0.8);
  backdrop-filter: blur(3px);
}
.logout-dialog {
  border: none;
  border-radius: 10px;
  clip-path: polygon(
    0 0,
    100% 10%,
    100% 100%,
    0 90%
  );
  padding: 0;
  width: 50%;
}
.dialog-inner {
  background-color: #a7ffed;
  padding: 10% 0;
}
.logout-message {
  color: #4e4e4e;
  font-size: clamp(0.1rem, 0.5vw + 0.9rem, 1.7rem);
  letter-spacing: 5px;
  margin-bottom: 10%;
  text-align: center;
}
.dialog-buttons {
  align-items: center;
  display: flex;
  justify-content: space-around;
}
.dialog-buttons__yes,
.dialog-buttons__no {
  background-color: #a7ffed;
  border: none;
  color: #4e4e4e;
  cursor: pointer;
  font-size: clamp(0.1rem, 0.3vw + 0.7rem, 1.4rem);
  font-weight: bold;
  letter-spacing: 3px;
  transition: color 0.5s;
}
.dialog-buttons__yes:hover,
.dialog-buttons__no:hover {
  color: #959595;
}

@media screen and (max-width: 768px) {
  .navMenu {
    box-shadow: 0 -4px 5px #bebebe;    
    display: flex;
    flex-direction: row;
    height: auto;
    overflow-x: auto;
    padding: 2% 0;
    position: static;
    width: 100%;
  }
  .navMenu:hover {
    width: 100%;
  }
  .navMenu-ul {
    align-items: center;
    display: flex;
    flex-direction: row;
    gap: 0;
    justify-content: space-around;
    margin: 0;
    padding: 0;
    width: 100%;
  }
  .navMenu-ul__item {
    margin-bottom: 0;
    padding: 10px;
  }
  .navMenu-ul__title {
    display: none;
  }
  .fa-solid {
    transition: 1s;
  }
  .fa-solid:hover {
    color: #4e4e4e;
  }
  .logout-dialog {
    width: 80%;
  }
  
}
</style>
