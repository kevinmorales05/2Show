/*==============================================================*/
/* DBMS name:      MySQL 5.0                                    */
/* Created on:     12/28/2020 7:04:47 PM                        */
/*==============================================================*/


alter table ANUNCIO 
   drop foreign key FK_ANUNCIO_ANUNCIOPR_COMPRAS_;

alter table ANUNCIO 
   drop foreign key FK_ANUNCIO_CONTRATAR_USUARIOS;

alter table ARTISTAS 
   drop foreign key FK_ARTISTAS_R1_EVENTOS;

alter table CANCIONES 
   drop foreign key FK_CANCIONE_SUBIR_ARTISTAS;

alter table COMPRAS_ANUNCIOS 
   drop foreign key FK_COMPRAS__ANUNCIOPR_ANUNCIO;

alter table COMPRAS_ANUNCIOS 
   drop foreign key FK_COMPRAS__COMPRARAN_USUARIOS;

alter table COMPRAS_USUARIO 
   drop foreign key FK_COMPRAS__COMPRARTI_USUARIOS;

alter table COMPRAS_USUARIO 
   drop foreign key FK_COMPRAS__RESERVAR_EVENTOS;

alter table DONACIONES 
   drop foreign key FK_DONACION_DONAR_USUARIOS;

alter table DONACIONES 
   drop foreign key FK_DONACION_RECIBIR_ARTISTAS;

alter table EVENTOS 
   drop foreign key FK_EVENTOS_PREMIAR_PREMIOS;

alter table EVENTOS 
   drop foreign key FK_EVENTOS_PROGRAMAR_ARTISTAS;

alter table EVENTOS 
   drop foreign key FK_EVENTOS_R1_ARTISTAS;

alter table EVENTOS 
   drop foreign key FK_EVENTOS_RESERVAR_COMPRAS_;

alter table POST_ARTISTAS 
   drop foreign key FK_POST_ART_POSTARTIS_ARTISTAS;

alter table POST_USUARIOS 
   drop foreign key FK_POST_USU_POSTUSER_USUARIOS;

alter table PREMIOS 
   drop foreign key FK_PREMIOS_GANAR_USUARIOS;

alter table PREMIOS 
   drop foreign key FK_PREMIOS_PREMIAR_EVENTOS;


alter table ANUNCIO 
   drop foreign key FK_ANUNCIO_CONTRATAR_USUARIOS;

alter table ANUNCIO 
   drop foreign key FK_ANUNCIO_ANUNCIOPR_COMPRAS_;

drop table if exists ANUNCIO;


alter table ARTISTAS 
   drop foreign key FK_ARTISTAS_R1_EVENTOS;

drop table if exists ARTISTAS;


alter table CANCIONES 
   drop foreign key FK_CANCIONE_SUBIR_ARTISTAS;

drop table if exists CANCIONES;


alter table COMPRAS_ANUNCIOS 
   drop foreign key FK_COMPRAS__COMPRARAN_USUARIOS;

alter table COMPRAS_ANUNCIOS 
   drop foreign key FK_COMPRAS__ANUNCIOPR_ANUNCIO;

drop table if exists COMPRAS_ANUNCIOS;


alter table COMPRAS_USUARIO 
   drop foreign key FK_COMPRAS__COMPRARTI_USUARIOS;

alter table COMPRAS_USUARIO 
   drop foreign key FK_COMPRAS__RESERVAR_EVENTOS;

drop table if exists COMPRAS_USUARIO;


alter table DONACIONES 
   drop foreign key FK_DONACION_DONAR_USUARIOS;

alter table DONACIONES 
   drop foreign key FK_DONACION_RECIBIR_ARTISTAS;

drop table if exists DONACIONES;


alter table EVENTOS 
   drop foreign key FK_EVENTOS_PROGRAMAR_ARTISTAS;

alter table EVENTOS 
   drop foreign key FK_EVENTOS_RESERVAR_COMPRAS_;

alter table EVENTOS 
   drop foreign key FK_EVENTOS_R1_ARTISTAS;

alter table EVENTOS 
   drop foreign key FK_EVENTOS_PREMIAR_PREMIOS;

drop table if exists EVENTOS;


alter table POST_ARTISTAS 
   drop foreign key FK_POST_ART_POSTARTIS_ARTISTAS;

drop table if exists POST_ARTISTAS;


alter table POST_USUARIOS 
   drop foreign key FK_POST_USU_POSTUSER_USUARIOS;

drop table if exists POST_USUARIOS;


alter table PREMIOS 
   drop foreign key FK_PREMIOS_GANAR_USUARIOS;

alter table PREMIOS 
   drop foreign key FK_PREMIOS_PREMIAR_EVENTOS;

drop table if exists PREMIOS;

drop table if exists USUARIOS;

/*==============================================================*/
/* Table: ANUNCIO                                               */
/*==============================================================*/
create table ANUNCIO
(
   ID_ADD               int not null  comment '',
   ID_COMPRA2           int  comment '',
   ID_USER              int not null  comment '',
   DES_ADD              varchar(254) not null  comment '',
   ALC_ADD              numeric(8,0) not null  comment '',
   COS_ADD              numeric(8,0) not null  comment '',
   TIP_ADD              varchar(254) not null  comment '',
   FEC_ADD              datetime not null  comment '',
   HOR_ADD              datetime not null  comment '',
   IMG_ADD              longblob  comment '',
   VID_ADD              varchar(254)  comment '',
   primary key (ID_ADD)
);

/*==============================================================*/
/* Table: ARTISTAS                                              */
/*==============================================================*/
create table ARTISTAS
(
   ID_USER2             int not null  comment '',
   ID_EVENT             int  comment '',
   NOM_ARTIST           varchar(254) not null  comment '',
   APE_ARTIST           varchar(254) not null  comment '',
   COR_ARTIST           varchar(254) not null  comment '',
   TEL_ARTIST           numeric(8,0) not null  comment '',
   CI_ARTIST            varchar(254) not null  comment '',
   PAS_ARTIST           varchar(254) not null  comment '',
   CIU_ARTIST           varchar(254) not null  comment '',
   DIR_ARTIST           varchar(254)  comment '',
   TIP_ARTIST           varchar(254) not null  comment '',
   CAT_ARTIST           varchar(254)  comment '',
   GEN_ARTIST           varchar(254) not null  comment '',
   GE2_ARTIST           varchar(254)  comment '',
   primary key (ID_USER2)
);

/*==============================================================*/
/* Table: CANCIONES                                             */
/*==============================================================*/
create table CANCIONES
(
   ID_SONG              int not null  comment '',
   ID_USER2             int not null  comment '',
   FIL_SONG             <AUDIO> not null  comment '',
   LYR_SONG             varchar(254) not null  comment '',
   ALB_SONG             varchar(254) not null  comment '',
   FEC_SONG             datetime not null  comment '',
   primary key (ID_SONG)
);

/*==============================================================*/
/* Table: COMPRAS_ANUNCIOS                                      */
/*==============================================================*/
create table COMPRAS_ANUNCIOS
(
   ID_COMPRA2           int not null  comment '',
   ID_USER              int not null  comment '',
   ID_ADD               int not null  comment '',
   FEC_COMPRAA          datetime not null  comment '',
   HOR_COMPRAA          datetime not null  comment '',
   TOT_COMPRAA          numeric(8,0) not null  comment '',
   primary key (ID_COMPRA2)
);

/*==============================================================*/
/* Table: COMPRAS_USUARIO                                       */
/*==============================================================*/
create table COMPRAS_USUARIO
(
   ID_COMPRA            int not null  comment '',
   ID_EVENT             int not null  comment '',
   ID_USER              int not null  comment '',
   FEC_COMPRAA          datetime not null  comment '',
   HOR_COMPRAA          datetime not null  comment '',
   CAN_COMPRA           int not null  comment '',
   TOT_COMPRAA          numeric(8,0) not null  comment '',
   TIP_COMPRA           varchar(254) not null  comment '',
   primary key (ID_COMPRA)
);

/*==============================================================*/
/* Table: DONACIONES                                            */
/*==============================================================*/
create table DONACIONES
(
   ID_DONACION          int not null  comment '',
   ID_USER2             int not null  comment '',
   ID_USER              int not null  comment '',
   CAN_DONACION         numeric(8,0)  comment '',
   FEC_DONACION         datetime  comment '',
   primary key (ID_DONACION)
);

/*==============================================================*/
/* Table: EVENTOS                                               */
/*==============================================================*/
create table EVENTOS
(
   ID_EVENT             int not null  comment '',
   ID_COMPRA            int  comment '',
   ID_PREMIO            int  comment '',
   ID_USER2             int not null  comment '',
   ART_ID_USER2         int not null  comment '',
   DAT_EVENT            datetime not null  comment '',
   HOR_EVENT            datetime not null  comment '',
   TIC_EVENT            int not null  comment '',
   COS_EVENT            numeric(8,0) not null  comment '',
   GOL_EVENT            numeric(8,0) not null  comment '',
   DON_EVENT            numeric(8,0)  comment '',
   IMG_EVENT            longblob  comment '',
   VID_EVENT            varchar(254)  comment '',
   DES_EVENT            varchar(254) not null  comment '',
   primary key (ID_EVENT)
);

/*==============================================================*/
/* Table: POST_ARTISTAS                                         */
/*==============================================================*/
create table POST_ARTISTAS
(
   ID_POST2             int not null  comment '',
   ID_USER2             int not null  comment '',
   DAT_POSTA            datetime not null  comment '',
   HOR_POSTA            datetime not null  comment '',
   TXT_POSTA            varchar(254)  comment '',
   IMG_POSTA            longblob  comment '',
   VID_POSTA            varchar(254)  comment '',
   primary key (ID_POST2)
);

/*==============================================================*/
/* Table: POST_USUARIOS                                         */
/*==============================================================*/
create table POST_USUARIOS
(
   ID_POST              int not null  comment '',
   ID_USER              int not null  comment '',
   DAT_POSTA            datetime not null  comment '',
   HOR_POSTA            datetime not null  comment '',
   TXT_POSTA            varchar(254)  comment '',
   IMG_POSTA            longblob  comment '',
   VID_POSTA            varchar(254)  comment '',
   primary key (ID_POST)
);

/*==============================================================*/
/* Table: PREMIOS                                               */
/*==============================================================*/
create table PREMIOS
(
   ID_PREMIO            int not null  comment '',
   ID_USER              int not null  comment '',
   ID_EVENT             int  comment '',
   DES_PREMIO           varchar(254) not null  comment '',
   FEC_PREMIO           datetime not null  comment '',
   primary key (ID_PREMIO)
);

/*==============================================================*/
/* Table: USUARIOS                                              */
/*==============================================================*/
create table USUARIOS
(
   ID_USER              int not null  comment '',
   NOM_ARTIST           varchar(254) not null  comment '',
   APE_ARTIST           varchar(254) not null  comment '',
   COR_ARTIST           varchar(254) not null  comment '',
   TEL_ARTIST           numeric(8,0) not null  comment '',
   CI_ARTIST            varchar(254) not null  comment '',
   PAS_ARTIST           varchar(254) not null  comment '',
   CIU_ARTIST           varchar(254) not null  comment '',
   DIR_ARTIST           varchar(254)  comment '',
   primary key (ID_USER)
);

alter table ANUNCIO add constraint FK_ANUNCIO_ANUNCIOPR_COMPRAS_ foreign key (ID_COMPRA2)
      references COMPRAS_ANUNCIOS (ID_COMPRA2) on delete restrict on update restrict;

alter table ANUNCIO add constraint FK_ANUNCIO_CONTRATAR_USUARIOS foreign key (ID_USER)
      references USUARIOS (ID_USER) on delete restrict on update restrict;

alter table ARTISTAS add constraint FK_ARTISTAS_R1_EVENTOS foreign key (ID_EVENT)
      references EVENTOS (ID_EVENT) on delete restrict on update restrict;

alter table CANCIONES add constraint FK_CANCIONE_SUBIR_ARTISTAS foreign key (ID_USER2)
      references ARTISTAS (ID_USER2) on delete restrict on update restrict;

alter table COMPRAS_ANUNCIOS add constraint FK_COMPRAS__ANUNCIOPR_ANUNCIO foreign key (ID_ADD)
      references ANUNCIO (ID_ADD) on delete restrict on update restrict;

alter table COMPRAS_ANUNCIOS add constraint FK_COMPRAS__COMPRARAN_USUARIOS foreign key (ID_USER)
      references USUARIOS (ID_USER) on delete restrict on update restrict;

alter table COMPRAS_USUARIO add constraint FK_COMPRAS__COMPRARTI_USUARIOS foreign key (ID_USER)
      references USUARIOS (ID_USER) on delete restrict on update restrict;

alter table COMPRAS_USUARIO add constraint FK_COMPRAS__RESERVAR_EVENTOS foreign key (ID_EVENT)
      references EVENTOS (ID_EVENT) on delete restrict on update restrict;

alter table DONACIONES add constraint FK_DONACION_DONAR_USUARIOS foreign key (ID_USER)
      references USUARIOS (ID_USER) on delete restrict on update restrict;

alter table DONACIONES add constraint FK_DONACION_RECIBIR_ARTISTAS foreign key (ID_USER2)
      references ARTISTAS (ID_USER2) on delete restrict on update restrict;

alter table EVENTOS add constraint FK_EVENTOS_PREMIAR_PREMIOS foreign key (ID_PREMIO)
      references PREMIOS (ID_PREMIO) on delete restrict on update restrict;

alter table EVENTOS add constraint FK_EVENTOS_PROGRAMAR_ARTISTAS foreign key (ID_USER2)
      references ARTISTAS (ID_USER2) on delete restrict on update restrict;

alter table EVENTOS add constraint FK_EVENTOS_R1_ARTISTAS foreign key (ART_ID_USER2)
      references ARTISTAS (ID_USER2) on delete restrict on update restrict;

alter table EVENTOS add constraint FK_EVENTOS_RESERVAR_COMPRAS_ foreign key (ID_COMPRA)
      references COMPRAS_USUARIO (ID_COMPRA) on delete restrict on update restrict;

alter table POST_ARTISTAS add constraint FK_POST_ART_POSTARTIS_ARTISTAS foreign key (ID_USER2)
      references ARTISTAS (ID_USER2) on delete restrict on update restrict;

alter table POST_USUARIOS add constraint FK_POST_USU_POSTUSER_USUARIOS foreign key (ID_USER)
      references USUARIOS (ID_USER) on delete restrict on update restrict;

alter table PREMIOS add constraint FK_PREMIOS_GANAR_USUARIOS foreign key (ID_USER)
      references USUARIOS (ID_USER) on delete restrict on update restrict;

alter table PREMIOS add constraint FK_PREMIOS_PREMIAR_EVENTOS foreign key (ID_EVENT)
      references EVENTOS (ID_EVENT) on delete restrict on update restrict;

