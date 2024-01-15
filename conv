import streamlit as st
import pandas as pd
import tabula
from io import BytesIO

def read_pdf_tabula(file_content):
    dfs = tabula.read_pdf(file_content, pages='all', multiple_tables=True)
    df = pd.concat(dfs, ignore_index=True)
    return df

def main():
    st.title("PDF to DataFrame Converter")

    uploaded_file = st.file_uploader("Choose a PDF file", type="pdf")

    if uploaded_file is not None:
        st.write("File uploaded successfully!")

        # Read PDF text
        pdf_content = BytesIO(uploaded_file.read())
        df = read_pdf_tabula(pdf_content)

        # Display the DataFrame
        st.write("DataFrame from PDF:")
        st.write(df)

if __name__ == "__main__":
    main()
