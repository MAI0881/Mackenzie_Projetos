# Importação e junção dos arquivos CSV

Nessa etapa, importei as bibliotecas necessárias para realizar a junção de todos os arquivos, já que o dataset que encontrei apenas disponibilizava os arquivos separadamente por categoria de produto:
import os  # importa a biblioteca os, que permite interagir com o sistema operacional
import glob  # importa a biblioteca glob, que permite encontrar todos os arquivos que correspondem a um padrão de nome
import pandas as pd  # importa a biblioteca pandas e a renomeia como pd

os.chdir(r"C:\Users\Maiara\OneDrive\MACKENZIE\Amazon")  # define o diretório de trabalho para a pasta "Amazon" no OneDrive

extension = 'csv'  # define a extensão desejada para os arquivos a serem lidos como "csv"
all_filenames = [i for i in glob.glob('*.{}'.format(extension))]  # cria uma lista com o nome de todos os arquivos na pasta atual com a extensão "csv"

df = pd.concat([pd.read_csv(f) for f in all_filenames])  # concatena todos os arquivos da lista "all_filenames" em um único DataFrame "df"
df.to_csv("df.csv", index=False, encoding='utf-8-sig')  # salva o DataFrame "df" em um arquivo CSV chamado "df.csv", sem incluir o índice e usando a codificação "utf-8-sig"
