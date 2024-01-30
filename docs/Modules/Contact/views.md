---
sidebar_position: 3
---

# Views

The corresponding view for the contact form configuration file is called **form_html** within the views/Contact folder in the theme. 

Basic View Structure: 

```

<div class="row">
	<div class="col mb-5">

		<h1><?= $vs_page_title; ?></h1>

		<form class="row g-3" action="<?= caNavUrl($this->request, "", "Contact", "send"); ?>" method="post">
			<div class="col-md-4">
				<label for="inputName" class="form-label"><?= _t("Name"); ?></label>
				<input type="text" class="form-control" id="inputName" name="name" aria-label="enter name" placeholder="Enter name" required>
			</div>
			<div class="col-md-4">
				<label for="inputEmail" class="form-label"><?= _t("Email"); ?></label>
				<input type="email" class="form-control" id="inputEmail" name="email" aria-label="enter email" placeholder="Enter email" required>
			</div>

			<div class="col-md-9">
				<label for="message" class="form-label"><?= _t("Message"); ?></label>
  				<textarea class="form-control" id="message" rows="5" name="message" aria-label="enter message" required>{{{message}}}</textarea>
			</div>

			<div class="col-12">
				<button type="submit" class="btn btn-primary"><?= _t("Send"); ?></button>
			</div>
		</form>

	</div>
</div>

```

Talk about views, view structure and view variables