# Oscar

<p> -- 1) Quantas vezes Natalie Portman foi indicada ao Oscar</p>
<p>-- R: Ela foi indicada 3 vezes</p>
<p> Usando esse comando você Procura o nome do indicado: SELECT * FROM filmes where nome_do_indicado like '%Natalie Portman%';</p>

<p>-- 2) Quantos Oscars Natalie Portman ganhou?</p>
<p>-- R: 1 vez</p>
<p>SELECT COUNT(*) FROM filmes where nome_do_indicado like '%Natalie Portman%' and vencedor = 'True';</p>

<p>-- 3) Amy Adams já ganhou algum Oscar?</p>
<p>-- R: Não</p>
<p>SELECT COUNT(*) FROM filmes where nome_do_indicado like '%Amy Adams%' and vencedor = 'True';</p>

<p>-- 4) A série de filmes Toy Story ganhou um Oscar em quais anos?</p>
<p>-- R: Em 2011 e 2020</p>
<p>SELECT ano_cerimonia FROM filmes where filme like '%Toy Story%' and vencedor = 'True';</p>

<p>-- 5) A partir de que ano que a categoria "Actress" deixa de existir? </p>
<p>-- R: Em 1975</p>
<p>SELECT * FROM filmes where categoria like 'Actress' order by ano_filmagem desc;</p>

<p>-- 6) O primeiro Oscar para melhor Atriz foi para quem? Em que ano?</p>
<p>-- R: Foi para Janet Gaynor em 1928</p>
<p>SELECT nome_do_indicado, ano_cerimonia, categoria</p>
<p>FROM filmes</p>
<p>WHERE categoria = 'Actress' and vencedor = 'True'</p>
<p>ORDER BY ano_cerimonia</p>
<p>LIMIT 1;</p>

<p>-- 7) Na coluna/campo "Vencedor", altere todos os valores com "Sim" para 1 e todos os valores "Não" para 0.</p>
<p>UPDATE filmes SET vencedor = 0 where vencedor = 'False';</p>
<p>UPDATE filmes SET vencedor = 1 where vencedor = 'True';</p>

<p>-- 8) Em qual edição do Oscar "Crash" ganhou o prêmio principal?</p>
<p>-- R: Na 78° edição em 2006.</p>
<p>SELECT * FROM filmes where filme like '%Crash%' and vencedor = '1';</p>

<p>-- 9) Bom... dê um Oscar para um filme que merece muito, mas não ganhou.</p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) </p>
<p>values('2022', '2023', '95', 'MUSIC (Original Score)', 'Sofia Carson', 'Purple Hearts', '1');</p>

<p>-- 10)  filme Central do Brasil aparece no Oscar?</p>
<p>-- Sim, apareceu em 1999</p>
<p>SELECT * from filmes WHERE filme like '%Central Station%';</p>

<p>-- 11) Inclua no banco 3 filmes que nunca foram nem nomeados ao Oscar, mas que merecem ser. </p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('2012', '2014', '86', 'ACTOR', 'Paulo Gustavo', 'Minha Mãe é uma Peça', '1');</p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('1998', '2000', '72', 'BEST PICTURE', 'Guel Arraes, Producer', 'O Auto da Compadecida', '1' );</p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('2012', '2014', '86', 'ACTOR', 'Leandro Hassum' ,'Até que a Sorte Nos Separe', '1' );</p>

<p>-- 12) Pensando no ano em que você nasceu: Qual foi o Oscar de melhor filme, Melhor Atriz e Melhor Diretor?</p>
<p>-- R: Em 2003 o longa Chicago ganhou como melhor filme; Nicole Kidman,melhor atriz; Roman Polanski, melhor Diretor.</p>   
<p>SELECT * FROM filmes where ano_cerimonia = 2003 and categoria like '%BEST PICTURE%' and vencedor = '1';</p>
<p>SELECT * FROM filmes where ano_cerimonia = 2003 and categoria like '%ACTRESS%' and vencedor = '1';</p>
<p>SELECT * FROM filmes where ano_cerimonia = 2003 and categoria like '%ACTOR%' and vencedor = '1';</p>
<p>SELECT * FROM filmes where ano_cerimonia = 2003 and categoria like '%DIRECTING%' and vencedor = '1';</p>

<p>-- 13) Agora procure 7 atrizes que não sejam americanas, europeias ou brasileiras.  Vamos cadastrá-los no nosso banco com o prêmio que você quiser. </p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('2013', '2015', '87', 'BEST ACTRESS', "Lupita Nyong'o", '12 Anos de Escravidão', '1');</p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('2006', '2008', '80', 'BEST ACTRESS', 'Aïssa Maïga', 'Bamako', '1' );</p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('2010', '2012','84', 'BEST ACTRESS', 'Genevieve Nnaji', 'Ijé: The Journey', '1');</p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('2013', '2015', '87', 'BEST ACTRESS', 'Danai Gurira', 'Mother of George','1');</p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('2005', '2008', '80','BEST ACTRESS', 'Ziyi Zhang','Memórias de uma Gueixa','1');</p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('1999', '2001', '73','BEST ACTRESS', 'Aishwarya Rai Bachchan','Hum Dil De Chuke </p>Sanam','1');</p>
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES('2012', '2014', '86','BEST ACTRESS', 'Bae Doona','Cloud Atlas','1');

<p>-- 14) Agora vamos falar da sua vida. Me diga o nome de uma pessoa que você admira e o que ela fez na sua vida. Agora me diz: Quê prêmio essa pessoa merece? 
<p>-- R: A "Tia Malina" fez com que eu me apaixonasse ainda mais pela música. Ela é bem mais que uma professora, sempre me incentiva e me apoia em tudo.
<p>INSERT INTO filmes (ano_filmagem, ano_cerimonia, cerimonia, categoria, nome_do_indicado, filme, vencedor) VALUES ('2023', '2024', '96', 'BEST TEACHER', 'Marina Cavalcante', 'Singer House', '1');
