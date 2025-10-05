import streamlit as st

# Konfigurasi halaman
st.set_page_config(page_title="Affiliate Prompt Builder", page_icon="🧠")

st.title("🧠 Affiliate Prompt Builder")
st.write("Bikin prompt AI otomatis untuk konten affiliate TikTok.")

# Input form
karakter = st.text_input("Karakter sedang apa?")
suasana = st.text_input("Suasana seperti apa?")
produk = st.text_input("Produk apa yang sedang direview?")
gesture = st.text_input("Gerakan atau ekspresi karakter?")
angle = st.text_input("Angle kamera seperti apa?")
gaya = st.selectbox(
    "Gaya visual",
    ["Natural", "Cinematic", "Luxury", "Lifestyle", "Street"]
)

# Tombol generate
if st.button("Generate Prompt"):
    prompt = f"""
**Prompt AI:**

Karakter **{karakter}**, dalam suasana **{suasana}**, sedang mereview produk **{produk}**.  
Gerakan tubuh: **{gesture}**  
Angle kamera: **{angle}**  
Gaya visual: **{gaya}**

Hasilkan visual profesional untuk konten affiliate TikTok.
"""
    st.success("✅ Prompt berhasil dibuat!")
    st.code(prompt, language="markdown")
