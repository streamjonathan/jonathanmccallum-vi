---
title: "Gợi ý một nghệ sĩ"
slug: suggest-an-artist
---

Tôi rất thích được nghe về những nhạc sĩ và nghệ sĩ theo Chúa Giê-xu. Nếu bạn biết ai đó mà bạn muốn tôi viết về họ, phỏng vấn họ, hay làm video phản hồi về họ, hãy cho tôi biết ở đây.

Chỉ cần một cái tên và một đường liên kết — và vài lời về lý do tại sao là người đó. Tôi đọc mọi thứ gửi đến. Cảm ơn bạn rất nhiều.

Bạn có biết ai không? Chạm vào ảnh của họ, mẫu sẽ tự điền — rồi thêm vài lời về lý do tại sao là người đó và gửi đi.

<div class="suggest-carousel" role="list" aria-label="Những nhạc sĩ và nghệ sĩ mà bạn có thể gợi ý">
{% for artist in suggest_carousel %}
  <button type="button" class="suggest-pick" role="listitem" data-artist="{{ artist.name }}" data-link="{{ artist.profile }}" title="Gợi ý {{ artist.name }}">
    <img src="{{ artist.img }}" alt="{{ artist.name }}" loading="lazy" width="150" height="150">
    <span class="suggest-pick__name">{{ artist.name }}</span>
    <span class="suggest-pick__note">{{ artist.note }}</span>
  </button>
{% endfor %}
</div>

<p class="suggest-carousel__more">Hoặc gợi ý một người mới bên dưới — bất cứ ai mà bạn nghĩ tôi nên nghe về họ.</p>

Trang này không dành cho người dưới 18 tuổi.

<form id="suggest-form" class="suggest-form">
  <label for="suggest-artist">Tên nghệ sĩ</label>
  <input id="suggest-artist" name="artist" type="text" maxlength="200" placeholder="Tôi nên xem ai?" required>

  <label for="suggest-link">Liên kết hồ sơ mạng xã hội</label>
  <input id="suggest-link" name="link" type="url" maxlength="500" placeholder="https://www.instagram.com/…" required>

  <fieldset class="suggest-kinds">
    <legend>Tôi nên làm gì với họ?</legend>
    <label><input type="checkbox" name="kind" value="write"> Viết về họ</label>
    <label><input type="checkbox" name="kind" value="interview"> Phỏng vấn họ</label>
    <label><input type="checkbox" name="kind" value="reaction"> Làm video phản hồi về họ</label>
  </fieldset>

  <label for="suggest-why">Tại sao là người đó?</label>
  <textarea id="suggest-why" name="why" rows="3" maxlength="500" placeholder="Vài lời là đủ…"></textarea>

  <label for="suggest-name">Tên bạn <span class="optional">(không bắt buộc)</span></label>
  <input id="suggest-name" name="fromName" type="text" maxlength="100" placeholder="Để tôi có thể cảm ơn bạn">

  <label for="suggest-from-link">Liên kết hồ sơ mạng xã hội của bạn <span class="optional">(không bắt buộc)</span></label>
  <input id="suggest-from-link" name="fromLink" type="url" maxlength="500" placeholder="https://www.instagram.com/…">

  <button id="suggest-button" type="button">Gửi gợi ý</button>

  <p id="suggest-result" aria-live="polite"></p>
</form>
