---
layout: page
title: OCR and TTS
permalink: /ocr-tts/
---

<h1>Upload an Image</h1>
<form id="upload-form" enctype="multipart/form-data">
    <input type="file" id="file-input" name="file" accept="image/*" />
    <button type="button" onclick="uploadFile()">Upload</button>
</form>
<div id="audio-output"></div>

<script>
    async function uploadFile() {
        const input = document.getElementById('file-input');
        const file = input.files[0];
        const formData = new FormData();
        formData.append('file', file);

        const response = await fetch('/upload', {
            method: 'POST',
            body: formData
        });

        const data = await response.json();
        const audioUrl = data.audioUrl;

        const audioOutput = document.getElementById('audio-output');
        audioOutput.innerHTML = `<audio controls><source src="${audioUrl}" type="audio/mpeg"></audio>`;
    }
</script>
