---
layout: single
title: "Contatti"
permalink: /contact/
classes: labsd-wide justified-text
---

# Contatta il Laboratorio

Per informazioni, proposte di collaborazione, attività di ricerca, tesi, tirocini o approfondimenti sui temi d’interesse del Laboratorio, è possibile contattarci compilando il modulo seguente.

Il Laboratorio è aperto al confronto con studenti, ricercatori, professionisti sanitari e organizzazioni interessate alla trasformazione digitale in sanità.

## MODULO PER CONTATTI

<form class="labsd-contact-form" id="labsd-contact-form">
    <div class="labsd-honeypot" aria-hidden="true">
        <label for="website">Website</label>
        <input
            type="text"
            id="website"
            name="website"
            tabindex="-1"
            autocomplete="off">
    </div>
    <div class="labsd-contact-form__row">
        <div class="labsd-contact-form__field labsd-floating-field">
            <input type="text" id="name" name="name" placeholder=" " required>
            <label for="name">Nome e Cognome</label>
        </div>
        <div class="labsd-contact-form__field labsd-floating-field">
            <input type="email" id="email" name="email" placeholder=" " required>
            <label for="email">Email</label>
        </div>
    </div>
    <div class="labsd-contact-form__field labsd-floating-field">
        <input type="text" id="subject" name="subject" placeholder=" " required>
        <label for="subject">Oggetto della richiesta</label>
    </div>
    <div class="labsd-contact-form__profile-simple">
        <div class="labsd-contact-form__profile-title">
            Ruolo
        </div>
        <label class="labsd-radio">
            <input type="radio" name="profile" value="studente-universitario" required>
            <span>Studente universitario</span>
        </label>
        <label class="labsd-radio">
            <input type="radio" name="profile" value="azienda-sanitaria-irccs">
            <span>Dipendente di un'azienda sanitaria o di un IRCCS</span>
        </label>
        <label class="labsd-radio">
            <input type="radio" name="profile" value="docente-ricercatore">
            <span>Docente / ricercatore universitario</span>
        </label>
        <label class="labsd-radio">
            <input type="radio" name="profile" value="altro" id="profile-other-radio">
            <span>Altro</span>
        </label>
        <div id="profile-other-wrapper" class="labsd-contact-form__profile-other" hidden>
            <div class="labsd-floating-field">
                <input type="text" id="profile-other" name="profile_other" placeholder=" ">
                <label for="profile-other">Specificare</label>
            </div>
        </div>
    </div>
    <div class="labsd-contact-form__interest">
        <label class="labsd-contact-form__interest-toggle">
        <input type="checkbox" id="interest-related" name="interest_related">
            Sto contattando il Laboratorio in relazione a uno specifico tema d'interesse
        </label>
    </div>
    <div id="interest-fields" class="labsd-contact-form__interest-fields" hidden>
        <div class="labsd-contact-form__row labsd-contact-form__row--topics">
            <div class="labsd-contact-form__field">
                <label for="interest-area">Categoria</label>
                <select id="interest-area" name="interest_area">
                    <option value="">Seleziona una categoria</option>
                    {% for area in site.data.available_topics_areas %}
                    <option value="{{ area.id }}">
                        {{ area.title }}
                    </option>
                    {% endfor %}
                </select>
            </div>
            <div class="labsd-contact-form__field">
                <label for="interest-topic">Tema d'interesse</label>
                <select id="interest-topic" name="interest_topic" disabled>
                    <option value="">Seleziona prima una categoria</option>
                </select>
            </div>
        </div>
    </div>
    <div class="labsd-contact-form__field labsd-floating-field">
        <textarea id="message" name="message" rows="5" placeholder=" " required></textarea>
        <label for="message">Messaggio</label>
    </div>
    <div class="labsd-contact-form__privacy">
    <label class="labsd-contact-form__privacy-toggle">
        <input type="checkbox" name="privacy" required>
        <span>Ho letto l'<a href="/privacy-policy">informativa sul trattamento dei dati personali</a>.</span>
    </label>
    </div>
    <input type="hidden" id="interest-area-label" name="interest_area_label">
    <input type="hidden" id="interest-topic-label" name="interest_topic_label">
    <div class="labsd-contact-form__actions">
        <button type="submit" id="contact-submit" class="btn btn--primary">
            Invia messaggio
        </button>
    </div>
    <div id="contact-form-status" class="labsd-contact-form__status" aria-live="polite"></div>
</form>

<script>
document.addEventListener("DOMContentLoaded", function () {

  const interestCheckbox = document.getElementById("interest-related");
  const interestFields = document.getElementById("interest-fields");
  const areaSelect = document.getElementById("interest-area");
  const topicSelect = document.getElementById("interest-topic");

  const topics = [
    {% for topic in site.data.available_topics %}
      {
        id: {{ topic.id | jsonify }},
        title: {{ topic.title | jsonify }},
        areas: {{ topic.areas | jsonify }}
      }{% unless forloop.last %},{% endunless %}
    {% endfor %}
  ];

  interestCheckbox.addEventListener("change", function () {

    interestFields.hidden = !this.checked;

    if (!this.checked) {
      areaSelect.value = "";

      topicSelect.innerHTML =
        '<option value="">Seleziona prima una categoria</option>';

      topicSelect.disabled = true;
    }

  });

  areaSelect.addEventListener("change", function () {

    const selectedArea = this.value;

    topicSelect.innerHTML = "";

    if (!selectedArea) {
      topicSelect.innerHTML =
        '<option value="">Seleziona prima una categoria</option>';

      topicSelect.disabled = true;
      return;
    }

    const filteredTopics = topics.filter(function (topic) {
      return topic.areas && topic.areas.includes(selectedArea);
    });

    topicSelect.innerHTML =
      '<option value="">Seleziona un tema</option>';

    filteredTopics.forEach(function (topic) {

      const option = document.createElement("option");

      option.value = topic.id;
      option.textContent = topic.title;

      topicSelect.appendChild(option);

    });

    topicSelect.disabled = false;

  });

});


document.addEventListener("DOMContentLoaded", function () {

  const form = document.getElementById("labsd-contact-form");
  const submitButton = document.getElementById("contact-submit");
  const status = document.getElementById("contact-form-status");

  const areaSelect = document.getElementById("interest-area");
  const topicSelect = document.getElementById("interest-topic");

  const areaLabel = document.getElementById("interest-area-label");
  const topicLabel = document.getElementById("interest-topic-label");

  const endpoint =
    "https://script.google.com/macros/s/AKfycbx3SxflWJv8ZKlg_pK02qp9zW13lih-NoXGgSca2LTh4aJnbPdTk55eStnTvtkDHp4k/exec";

  form.addEventListener("submit", async function (event) {

    event.preventDefault();

    if (!form.checkValidity()) {
      form.reportValidity();
      return;
    }

    // Salva anche le descrizioni leggibili di categoria e topic
    if (areaSelect && areaSelect.selectedIndex >= 0) {
      areaLabel.value =
        areaSelect.options[areaSelect.selectedIndex].text.trim();
    }

    if (
      topicSelect &&
      !topicSelect.disabled &&
      topicSelect.selectedIndex >= 0
    ) {
      topicLabel.value =
        topicSelect.options[topicSelect.selectedIndex].text.trim();
    } else {
      topicLabel.value = "";
    }

    submitButton.disabled = true;
    submitButton.textContent = "Invio in corso...";

    status.textContent = "";
    status.className = "labsd-contact-form__status";

    try {

      const formData = new FormData(form);

      await fetch(endpoint, {
        method: "POST",
        body: formData,
        mode: "no-cors"
      });

      status.textContent =
        "Messaggio inviato correttamente. Grazie per aver contattato il Laboratorio.";

      status.classList.add(
        "labsd-contact-form__status--success"
      );

      form.reset();

      // Ripristina eventuali campi condizionali
      const interestFields =
        document.getElementById("interest-fields");

      if (interestFields) {
        interestFields.hidden = true;
      }

      if (topicSelect) {
        topicSelect.disabled = true;
        topicSelect.innerHTML =
          '<option value="">Seleziona prima una categoria</option>';
      }

      areaLabel.value = "";
      topicLabel.value = "";

    } catch (error) {

      console.error(error);

      status.textContent =
        "Si è verificato un problema durante l'invio. Riprova più tardi.";

      status.classList.add(
        "labsd-contact-form__status--error"
      );

    } finally {

      submitButton.disabled = false;
      submitButton.textContent = "Invia messaggio";

    }

  });

});

document.addEventListener("DOMContentLoaded", function () {

  const profileRadios =
    document.querySelectorAll('input[name="profile"]');

  const otherRadio =
    document.getElementById("profile-other-radio");

  const otherWrapper =
    document.getElementById("profile-other-wrapper");

  const otherInput =
    document.getElementById("profile-other");

  profileRadios.forEach(function (radio) {

    radio.addEventListener("change", function () {

      if (otherRadio.checked) {

        otherWrapper.hidden = false;
        otherInput.required = true;
        otherInput.focus();

      } else {

        otherWrapper.hidden = true;
        otherInput.required = false;
        otherInput.value = "";

      }

    });

  });

});

</script>