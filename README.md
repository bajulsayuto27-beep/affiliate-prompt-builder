
import streamlit as st

st.set_page_config(page_title="Affiliate Prompt Builder", page_icon="🧠")

st.title("🧠 Affiliate Prompt Builder")
st.write("Bikin prompt AI otomatis untuk konten affiliate TikTok dari satu gambar produk jadi 10 ide konten.")

# Form input
with st.form("affiliate_form"):
    karakter = st.text_input("Karakter sedang apa?")
    suasana = st.text_input("Suasana seperti apa?")
    produk = st.text_input("Produk apa yang sedang direview?")
    gesture = st.text_input("Gerakan atau ekspresi karakter?")
    angle = st.text_input("Angle kamera seperti apa?")
    gaya = st.selectbox("Gaya visual", ["Natural", "Cinematic", "Luxury", "Lifestyle", "Street"])
    submitted = st.form_submit_button("Generate Prompt")

if submitted:
    prompt = f"""
Karakter **{karakter}** dalam suasana **{suasana}**, sedang mereview produk **{produk}**.  
Gerakan tubuh: **{gesture}**  
Angle kamera: **{angle}**  
Gaya visual: **{gaya}**

Hasilkan 10 variasi konten video profesional untuk TikTok Affiliate.
"""
    st.success("✅ Prompt berhasil dibuat!")
    st.code(prompt, language="markdown")
