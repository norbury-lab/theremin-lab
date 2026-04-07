---
title: お問い合わせ
layout: default
nav_order: 120
---

# お問い合わせ

テルミンに関すること、修理・DIYの相談、資料の情報提供など、
お気軽にどうぞ。返信に時間がかかる場合があります。

<form action="https://formspree.io/f/mykbwddy" method="POST">
  <div style="margin-bottom: 1rem;">
    <label for="name" style="display:block; margin-bottom:.3rem; font-weight:bold;">お名前（任意）</label>
    <input type="text" id="name" name="name"
      style="width:100%; max-width:500px; padding:.5rem; border:1px solid #ccc; border-radius:4px; font-size:1rem;">
  </div>
  <div style="margin-bottom: 1rem;">
    <label for="email" style="display:block; margin-bottom:.3rem; font-weight:bold;">メールアドレス</label>
    <input type="email" id="email" name="email"
      style="width:100%; max-width:500px; padding:.5rem; border:1px solid #ccc; border-radius:4px; font-size:1rem;">
  </div>
  <div style="margin-bottom: 1rem;">
    <label for="message" style="display:block; margin-bottom:.3rem; font-weight:bold;">メッセージ <span style="color:red;">*</span></label>
    <textarea id="message" name="message" rows="7" required
      style="width:100%; max-width:500px; padding:.5rem; border:1px solid #ccc; border-radius:4px; font-size:1rem; resize:vertical;"></textarea>
  </div>
  <input type="hidden" name="_subject" value="テルミン・ラボへのお問い合わせ">
  <button type="submit"
    style="background:#333; color:#fff; border:none; padding:.6rem 1.5rem; border-radius:4px; font-size:1rem; cursor:pointer;">
    送信する
  </button>
</form>