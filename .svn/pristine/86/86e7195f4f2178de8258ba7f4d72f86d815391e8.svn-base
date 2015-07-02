//
//            this program is designed for mao jin xiu ji tou ban
//         

#include  <msp430x14x.h>


#include <stdlib.h>

#define uchar unsigned char
#define u8 unsigned char
#define U8 u8
#define uint unsigned int
#define u16 uint 
#define U16 u16
#define PORTD P1OUT
#define DE 0x04
#define RE 0x40
 
u8 mode,fflaga,fflagb;
u16 pointer5;

u8 startdo, shandeng,pa,pa_old,pa1,b_lock,b_buxiu,a_lock,a_buxiu,headcode,tem;

u8 moveafinish=1,movebfinish=1; 
                          
u8 getchar1;

uchar addreffect=0,atzero,buxiu_flage,jiwei,positiona,positionb;

u16 error,adcvaluea,adcvalueb,posivalueb,posivaluea,adcvalueaold1,adcvaluebold1;

uint adcxa,adcxb,adcvaluebold,adcvalueaold;

u8 huiwei,halfjian,jian,tiaoshiflag,jiandaoshuju,zhengaoshuju;

u16 halfanglejian,halfanglejian1,halfanglejian2,anglejian,anglejian1,anglejian2,anglejian3,anglejian4;

u8 pd,pdcw,pdtest,pdtimes; 

u16 pdangle,pdangle1,pdangle2,pdxs,pdspeed,ta6;

u8 describe,mingling,shu,shuju,jiaodu,sudu,headcode1,ccw,swshuju,djshuju,djshuju1,Dshuju;
u16 shu3,shu4,shu31,shu32,shu41,other,speed;


u8 jitou,jianxian,daoweia,daoweib,s5,s6,s511,s611,s5tem,s6tem,jiejin,HH,flag5,pointer6,pointer8,jiantest;
u16 Ta2,Ta3,Ta4,m2,angle1,AN3,ang1,TD,m3;

u8 HHH,maojinccw,maojinccw1,AN4,flag6,Huansecw,s7,s7tem,s8,s8tem,jianxiancs,jitoucs,tr,HHmove,AN5,yuanshuju,chuanshuju,zhenwei;
u16 maojinspeedold,maojinspeed,Dxs,DXS2,Hxs,Hxs1,HXS2,Huanseangle1,HSspeed,HHspeed,maojinangle,maojinangle1,djzt,djzt1,djzt2,djzt3;

int yu,yu1,pdyu,PYyu=0,PYangle3,PYangle2,angle2,maojinangle2,halfyu=0;
u8 PYspeed;
u16 PYangle1,PYangle,PYxs;

u16 m1,m,angle,AN,V1,v2,n1,AN1,AN2,angel1,zhenangle1,zhenangle,zhenangle2,Huanseangle,HSxs,HHxs,zhenxs;

u8 pointer1,pointer2,pointer3,pointer4,P,k1,ADDATAH,cw1,cw2,STOP,h1,h2,PWM,CURRENTVALUE1,E,n;
u8 step1,step2,j1,s1,s2,m4,m5,m6,huanse,Hsshuju1,Hsshuju2,a_lock1,b_lock1,fheadcode,jtshuju,yiwei,jtshu,addressflag;

u8 crcshuju,crc1,crc2,data1,PYshuju,error11,error12,duanjian,duanjian1,duanjian2;
u16 crc,crc3,crc11,jiandaochaoshi;

u8 daoweia1=0,daoweib1=0,Hdaowei=0,Hdaoweitimes=0;
u8 chajiejin=0,jiejintimes=0;
unsigned long shu1,shu2,shuju32,shu11,shu21,H1v2,H2v2,Dv2,Hxs16,Dxs16,H1v3,H1quxian;

int UARTSHUJU,putdata1;
u8  uartshu,spi,firsta1,uartshu1,reshu,zhencw,maojinccw1,PYcw,BMMODE,BMTEST,reshu1;
u8  positionaold,positionbold,position,position1,positiona1,positionb1,error21,error22,Hdaowei1,s7tem1,s7tem2,s8tem1,s8tem2;				
u16 maxa,mina,maxb,minb,needlehigh,needleangle,m9,needlehigh1,needlehigh2,zhenspeed;
u8  cwneedlehigh,zhentestshuju,jitoutest,zhenspeed1,uarttestshuju,uartempty;
u8  firstona,firstonb,ZXS;
u16 chaoshi1,HHmove1,putdata2;
u8  headcodex;

int hdposition,hdpositionold;
u8 h1flag,shangdian,chuanxianflag,zhenweiold;

u8 buc,bcshuju,HHangle1,HHshuju1,VATH,jiandaoshuju1,boardnum,banshuju;

int H4POS;
//u16 H1quxian; 
unsigned char CURRENTVALUEa1[64];
unsigned char CURRENTVALUEb1[64]; 


/* Local Variables - 16 bit */
 int PWMS1,i,ADDATA1,ADDATA2,ADDATA3,ADDATA4,ADDATA5,ADDATA6;
 int KV2;
const unsigned int posivalue[]={                                               // zhen gao position
                 //40,80,120,160,200,240,280,320,360,400,1000 };
                 //  40,72,104,136,168,200,232,264,296,328,844 };
                 // 40,68,96,124,152,180,208,236,264,292,852};
                    844,812,780,748,716,684,652,620,588,556,80};                       
	 

                 
U8 senddata[6];

                 
 //const unsigned int timedata1[1][42]={9000,6000,4000,2500,1500,1000,800,750,700,650,600,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550,550};               
                 
//const unsigned char KV[]={128,128,64,64,56,56,48,48,44,44,40,40,36,36,32,32,32,32,28,28,28,28,28,28,24,24,24,24,24,24,24,24,22,22,22,22,22,22,22,22,20,20,20,20,20,20,20,20,19,19,19,19,19,19,19,19,18,18,18,18,18,18,18,18,18,18,18,18,18,18,17,17,17,17,17,17,17,17,17,17,17,17,17,17,17,17,16,16};              

//const unsigned char Hquxian[]={200,200,150,150,120,120,120,100,100,100,85,85,85,70,70,70,60,60,60,60,55,55,55,55,51,51,51,51,48,48,48,48,45,45,45,45,43,43,43,43,42,42,42,42,41,41,41,41,40,40,40,40};         //,20,20,20,20,20,20,20,20,20,20,20,20,20,20,20,20,20,20,18,18,18,18,18,18,18,18,18,18,18,18,18,18,18,18};            

extern const unsigned char Hquxian1[];

extern const unsigned char HSquxian1[];
extern const unsigned char Hquxian2[];      //pjz 20061009

extern const unsigned char Hquxian3[];      //pjz 20061009

extern const unsigned char Hquxian4[];     //pjz 20070122

extern const unsigned int HXSA1[];      //pjz 20061009

extern const unsigned int HXSA2[];

extern const unsigned int HXSA3[]; //pjz 20070122

extern const unsigned char Dquxian1[];

extern const unsigned int DXSA1[];      //pjz 20061009

extern const unsigned int V_VALUE[];

extern const unsigned short crc_ta[];


//const unsigned char pdquxian[]={200,200,200,200,150,150,150,150,150,120,120,120,120,90,90,90,90,65,65,65,65,60,60,60,60,55,55,55,55,50,50,50,50,45,45,45,45,40,40,40,40};
               
//const unsigned char HSquxian[]={200};
                                
//unsigned int timedata[38];
 //                                current table
 
//const unsigned char  PWM1A[]={110,110,110,110,109,109,109,108,107,107,106,105,104,103,102,101,100,101,102,103,104,105,106,107,107,108,109,109,109,110,110,110,110,110,110,110,109,109,109,108,107,107,106,105,104,103,102,101,100,101,102,103,104,105,106,107,107,108,109,109,109,110,110,110};
//const unsigned char  PWM1A[]={0x3d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d,0x7d};


const unsigned char  PWM1A1[]={110,110,110,110,110,109,109,108,107,107,106,105,104,103,102,101,100,99,98,97,96,95,94,93,93,92,91,91,90,90,90,90,90,90,90,90,90,91,91,92,93,93,94,95,96,97,98,99,100,101,102,103,104,105,106,107,107,108,109,109,110,110,110,110};

//const unsigned char  PWM1A1[]={110,110,110,110,109,109,108,108,107,106,106,105,104,103,102,101,100,99,98,97,96,95,94,94,93,92,92,91,91,90,90,90,90,90,90,90,91,91,92,92,93,94,94,95,96,97,98,99,100,101,102,103,104,105,106,106,107,108,108,109,109,110,110,110};

const unsigned char  PWM1A2[]={105,105,105,105,105,105,105,104,104,104,103,103,102,102,101,101,100,99,99,98,98,97,97,96,96,95,95,95,95,95,95,95,95,95,95,95,95,95,95,96,96,96,97,97,98,98,99,99,100,100,101,102,102,103,103,104,104,105,105,105,105,105,105,105};

//const unsigned char  CURRENTA[]={151,151,151,150,149,148,147,145,144,142,140,138,136,133,131,128,126,124,121,119,116,114,112,110,108,107,105,104,103,102,101,101,101,101,101,102,103,104,105,107,108,110,112,114,116,119,121,124,126,128,131,133,136,138,140,142,144,145,147,148,149,150,151,151};

//const unsigned char  CURRENT0A[]={138,138,138,138,137,137,136,136,135,134,134,133,132,131,130,129,128,127,126,125,124,123,122,122,121,120,120,119,119,118,118,118,118,118,118,118,119,119,120,120,121,122,122,123,124,125,126,127,128,129,130,131,132,133,134,134,135,136,136,137,137,138,138,138};
//0.3A
//const unsigned char  CURRENT1A[]={141,141,141,140,140,139,138,138,137,136,134,133,132,130,129,127,126,125,123,122,120,119,118,116,115,114,114,113,112,112,111,111,111,111,111,112,112,113,114,114,115,116,118,119,120,122,123,125,126,127,129,130,132,133,134,136,137,138,138,139,140,140,141,141};
// 0.5A

//const unsigned char  CURRENT1A1[]={157,157,156,156,155,153,152,150,148,146,143,141,138,135,132,129,126,123,120,117,114,111,109,106,104,102,100,99,97,96,96,95,95,95,96,96,97,99,100,102,104,106,109,111,114,117,120,123,126,129,132,135,138,141,143,146,148,150,152,153,155,156,156,157};
// 1A

//const unsigned char  CURRENT1A2[]={172,172,171,170,169,167,164,162,159,155,152,148,144,139,135,131,126,121,117,113,108,104,100,97,93,90,88,85,83,82,81,80,80,80,81,82,83,85,88,90,93,97,100,104,108,113,117,121,126,131,135,139,144,148,152,155,159,162,164,167,169,170,171,172};
// 1.5A

const unsigned char  CURRENT1A3[]={187,187,186,184,182,180,177,173,169,165,160,155,149,144,138,132,126,120,114,108,103,97,92,87,83,79,75,72,70,68,66,65,65,65,66,68,70,72,75,79,83,87,92,97,103,108,114,120,126,132,138,144,149,155,160,165,169,173,177,180,182,184,186,187};
// 2A选择1.2A电流

const unsigned char  CURRENT1A4[]={203,203,202,200,197,194,190,186,180,175,169,162,155,148,141,134,126,118,111,104,97,90,83,77,72,66,62,58,55,52,50,49,49,49,50,52,55,58,62,66,72,77,83,90,97,104,111,118,126,134,141,148,155,162,169,175,180,186,190,194,197,200,202,203};
// 2.5A

//const unsigned char  CURRENT1A5[]={218,218,216,214,211,207,203,197,191,184,177,169,161,153,144,135,126,117,108,99,91,83,75,68,61,55,49,45,41,38,36,34,34,34,36,38,41,45,49,55,61,68,75,83,91,99,108,117,126,135,144,153,161,169,177,184,191,197,203,207,211,214,216,218};
// 3A

//const unsigned char  CURRENT1A6[]={234,233,232,229,226,221,216,209,202,195,186,177,167,157,147,137,126,115,105,95,85,75,66,57,50,43,36,31,26,23,20,19,18,19,20,23,26,31,36,43,50,57,66,75,85,95,105,115,126,137,147,157,167,177,186,195,202,209,216,221,226,229,232,233};
// 3.5A


const unsigned char  CURRENT1A1[]={159,159,158,157,156,155,154,152,150,147,145,142,140,137,134,131,128,125,122,119,116,114,111,109,106,104,102,101,100,99,98,97,97,97,98,99,100,101,102,104,106,109,111,114,116,119,122,125,128,131,134,137,140,142,145,147,150,152,154,155,156,157,158,159};
//1A
//const unsigned char  PWM1B[]={100,101,102,103,104,105,106,107,107,108,109,109,109,110,110,110,110,110,110,110,109,109,109,108,107,107,106,105,104,103,102,101,100,101,102,103,104,105,106,107,107,108,109,109,109,110,110,110,110,110,110,110,109,109,109,108,107,107,106,105,104,103,102,101};
//const unsigned char  PWM1B[]={0x64,0x73,0x81,0x8e,0x99,0xa3,0xa9,0xad,0xaf,0xad,0xa9,0xa3,0x99,0x8e,0x81,0x73,0x64,0x55,0x47,0x3a,0x2f,0x25,0x1f,0x1b,0x19,0x1b,0x1f,0x25,0x2f,0x3a,0x47,0x55};

//const unsigned char  PWM1B1[]={100,99,98,97,96,95,94,93,93,92,91,91,90,90,90,90,90,90,90,90,90,91,91,92,93,93,94,95,96,97,98,99,100,101,102,103,104,105,106,107,107,108,109,109,110,110,110,110,110,110,110,110,110,109,109,108,107,107,106,105,104,103,102,101};


const unsigned char  PWM1B1[]={100,99,98,97,96,95,94,93,93,92,91,91,90,90,90,90,90,90,90,90,90,91,91,92,93,93,94,95,96,97,98,99,100,101,102,103,104,105,106,107,107,108,109,109,110,110,110,110,110,110,110,110,110,109,109,108,107,107,106,105,104,103,102,101};

const unsigned char  PWM1B2[]={100,99,99,98,98,97,97,96,96,95,95,95,95,95,95,95,95,95,95,95,95,95,95,96,96,96,97,97,98,98,99,99,100,100,101,102,102,103,103,104,104,105,105,105,105,105,105,105,105,105,105,105,105,105,105,104,104,104,103,103,102,102,101,101};


//const unsigned char  PWM1B1[]={100,99,98,97,96,95,94,94,93,92,92,91,91,90,90,90,90,90,90,90,91,91,92,92,93,94,94,95,96,97,98,99,100,101,102,103,104,105,106,106,107,108,108,109,109,110,110,110,110,110,110,110,109,109,108,108,107,106,106,105,104,103,102,101};

//const unsigned char  CURRENTB[]={126,124,121,119,116,114,112,110,108,107,105,104,103,102,101,101,101,101,101,102,103,104,105,107,108,110,112,114,116,119,121,124,126,128,131,133,136,138,140,142,144,145,147,148,149,150,151,151,151,151,151,150,149,148,147,145,144,142,140,138,136,133,131,128};
//const unsigned char  CURRENT0B[]={128,127,126,125,124,123,122,122,121,120,120,119,119,118,118,118,118,118,118,118,119,119,120,120,121,122,122,123,124,125,126,127,128,129,130,131,132,133,134,134,135,136,136,137,137,138,138,138,138,138,138,138,137,137,136,136,135,134,134,133,132,131,130,129};
//0.3A
//const unsigned char  CURRENT1B[]={126,125,123,122,120,119,118,116,115,114,114,113,112,112,111,111,111,111,111,112,112,113,114,114,115,116,118,119,120,122,123,125,126,127,129,130,132,133,134,136,137,138,138,139,140,140,141,141,141,141,141,140,140,139,138,138,137,136,134,133,132,130,129,127};
// 0.5A

//const unsigned char  CURRENT1B1[]={126,123,120,117,114,111,109,106,104,102,100,99,97,96,96,95,95,95,96,96,97,99,100,102,104,106,109,111,114,117,120,123,126,129,132,135,138,141,143,146,148,150,152,153,155,156,156,157,157,157,156,156,155,153,152,150,148,146,143,141,138,135,132,129};
// 1A

//const unsigned char  CURRENT1B2[]={126,121,117,113,108,104,100,97,93,90,88,85,83,82,81,80,80,80,81,82,83,85,88,90,93,97,100,104,108,113,117,121,126,131,135,139,144,148,152,155,159,162,164,167,169,170,171,172,172,172,171,170,169,167,164,162,159,155,152,148,144,139,135,131};
// 1.5A

const unsigned char  CURRENT1B3[]={126,120,114,108,103,97,92,87,83,79,75,72,70,68,66,65,65,65,66,68,70,72,75,79,83,87,92,97,103,108,114,120,126,132,138,144,149,155,160,165,169,173,177,180,182,184,186,187,187,187,186,184,182,180,177,173,169,165,160,155,149,144,138,132};
// 2A选择1.2A电流

const unsigned char  CURRENT1B4[]={126,118,111,104,97,90,83,77,72,66,62,58,55,52,50,49,49,49,50,52,55,58,62,66,72,77,83,90,97,104,111,118,126,134,141,148,155,162,169,175,180,186,190,194,197,200,202,203,203,203,202,200,197,194,190,186,180,175,169,162,155,148,141,134};
// 2.5A

//const unsigned char  CURRENT1B5[]={126,117,108,99,91,83,75,68,61,55,49,45,41,38,36,34,34,34,36,38,41,45,49,55,61,68,75,83,91,99,108,117,126,135,144,153,161,169,177,184,191,197,203,207,211,214,216,218,218,218,216,214,211,207,203,197,191,184,177,169,161,153,144,135};
// 3A

//const unsigned char  CURRENT1B6[]={126,115,105,95,85,75,66,57,50,43,36,31,26,23,20,19,18,19,20,23,26,31,36,43,50,57,66,75,85,95,105,115,126,137,147,157,167,177,186,195,202,209,216,221,226,229,232,233,234,233,232,229,226,221,216,209,202,195,186,177,167,157,147,137};
// 3.5A

const unsigned char  CURRENT1B1[]={128,125,122,119,116,114,111,109,106,104,102,101,100,99,98,97,97,97,98,99,100,101,102,104,106,109,111,114,116,119,122,125,128,131,134,137,140,142,145,147,150,152,154,155,156,157,158,159,159,159,158,157,156,155,154,152,150,147,145,142,140,137,134,131};
//1A

void port_init(void)      // I/O init
{ 
 P1DIR = 0xff;       //p1.4-7 is output lights  p1.3 dj1
 P1OUT = 0xf0;
 P2DIR = 0x0e;       //p20 error input,p21,p22 enable  output low,p2.3 output ;p26,p27 key4,key5 input,p2.3,p2.4 dipkey,p2.5 dj2;
 P2OUT = 0x08;
 P3SEL =0x30;        //p34,p35 txd,rxd selected;     
 P3DIR =0xc0;        //de:output =0,re:output =0, key0-3:input =0;      
 P3OUT =0x00;
 P4SEL=0x3e;         //p4.1-5:pwm mode;
 //P4DIR=0x3e;
 P4DIR=0x3f;         //p4.6,p4.7 input
 P5DIR=0x04;         //DIP3-10: input;                 oooooooooooooooooooooooo
 P5OUT=0x00;
 P5SEL=0x00;
 P6SEL=0xff;         //ADC input;
 P6DIR=0x0;  
 
}

void clockinit(void)                    // xtal init                     
{ 
  BCSCTL1 |= XTS;                        // ACLK = LFXT1 = High F XTAL
  //BCSCTL1 &= ~XT2OFF;                  // XT2 = HF XTAL
  do 
  {
    IFG1 &= ~OFIFG;                       // Clear OSCFault flag
    for (i = 0xFF; i > 0; i--);           // Time for flag to set
  }
  while ((IFG1 & OFIFG)  == OFIFG);     // OSCFault flag still set?   
  BCSCTL2 |= SELM1+SELM0;                // MCLK = LFXT1 (safe)
}
  
void usartinit(void)                    // usart0 init  
{
  UCTL0 = CHAR+MM;                 // 8-bit character+
  UTCTL0 = SSEL0;                       // UCLK = ACLK
  UBR00 = 0x50;                         // 8MHz 100000                2M 
  UBR10 = 0x00;                         // 8MHz 100000
  URCTL0=URXWIE;
  UMCTL0 = 0x00;                        // 8MHz 100000 modulation
  ME1 |= UTXE0+ URXE0;                  // Enable USART0 TXD/RXD
  IE1 |= URXIE0;                        // Enable USART0 RX interrupt                   
}
void TIMEA_3(void)                              //timera init
{
  TACTL = TASSEL0 + TACLR+ID0;              // ACLK, clear TAR  n2 div   
}

 void TIMEB_7(void)                              // timerb init (4 channel pwm)  
{
  TBCTL = TBSSEL_1 + TBCLR+CNTL_3;      // ACLK, clear TBR  8bits
  TBCCR0=200;                           // ACLK=8MHZ,PWM 20KHZ
  TBCCTL1=OUTMOD_2+CLLD_1;              // OUTPUT MODE 2 WHEN TBR=0 REFRESH
  TBCCR1=100;                           // 50% PWM DUTY
  TBCCTL2=OUTMOD_2+CLLD_1;              // OUTPUT MODE 2
  TBCCR2=100; 
  TBCCTL3=OUTMOD_2+CLLD_1;              // OUTPUT MODE 2
  TBCCR3=100;             
  TBCCTL4=OUTMOD_2+CLLD_1;              // OUTPUT MODE 2
  TBCCR4=100;       
}
 void ADCINIT(void)                              // adc12 init
 {
  // SET UP AD
  ADC12CTL0 &= ~ENC;
  ADC12CTL0 =MSC+ ADC12ON+SHT0_2;           // Turn on ADC12, set sampling time  
  ADC12CTL1 = SHP+ADC12DIV_3+ADC12SSEL_1+CONSEQ_3;// Use sampling timer adclk=Aclk,2 DIV start channel A0
  ADC12IE = 0x00;                       // Enable ADC12IE.0-5
  ADC12MCTL0 = SREF_2+INCH_0;           // Vr+ = VeREF+ (external) CHANNEL A0
  ADC12MCTL1 = SREF_2+INCH_1;           // Vr+ = VeREF+ (external) CHANNEL A1
  ADC12MCTL2 = SREF_2+INCH_2;           // Vr+ = VeREF+ (external) CHANNEL A2
  ADC12MCTL3 = SREF_2+INCH_3;           // Vr+ = VeREF+ (external) CHANNEL A3
  ADC12MCTL4 = SREF_2+INCH_4;           // Vr+ = VeREF+ (external) CHANNEL A4
  ADC12MCTL5 = SREF_2+INCH_5+EOS;           // Vr+ = VeREF+ (external) CHANNEL A5
  ADC12CTL0 |= ENC;                     // ADC12 enable
 }
 
 void delay(uint  delay_value)                      // delay
{
 uint i,j;
 for(i=0;i<delay_value;i++)
     for(j=0;j<100;j++)
          ;
} 
 
 void current_select(void) // current select by dip key
{ 
  u8 c1=0,c1tem=1;
  c1=P2IN&0x10;
  delay(10);
  c1tem=P2IN&0x10;
  while(c1!=c1tem)
  {
    c1=P2IN&0x10;
    delay(10);
    c1tem=P2IN&0x10;
  } // current select P2.3,P2.4
    if (c1==0)//第一个拨码开关，为低，1.2A电流
    { 
      for (j1=0;j1<64;j1++)
      {
        CURRENTVALUEa1[j1]=CURRENT1A4[j1];// 为什么两个表不一样？
        CURRENTVALUEb1[j1]=CURRENT1B4[j1];
        //mode=1;
      }
   }
    else if (c1==0x10)
   {
     for (j1=0;j1<64;j1++)
     {
        CURRENTVALUEa1[j1]=CURRENT1A3[j1]; // 
        CURRENTVALUEb1[j1]=CURRENT1B3[j1];
     }
   }
}     
void mode_select(void) //板功能选择，上下机头
{
  u8 mode1=0,mode1tem=0;
  mode1=P5IN&0x80;
  delay(10);
  mode1tem=P5IN&0x80;
  while(mode1!=mode1tem)
    {
      	mode1=P5IN&0x80;
       	delay(10);
       	mode1tem=P5IN&0x80;
    }
      if (mode1==0x80)// zhen gao 上机头
      {
      	HH=1;
       	mode=4;
       	headcodex=0xf0;//上机头公用地址
       	HHH=1;
       	jitou=1;
       	jianxian=0;
       	jitoucs=1;
       	pd=0;
      }
      else if(mode1==0x00)//剪线
     {
       HHH=1;
       HH=0;
       headcodex=0xe0;//下机头公用地址
       mode=1;
       jianxian=1;
       jianxiancs=1;
       jitou=0;
       pd=0;
     }
 }
 
void step_select(void)                                // micro step select (0.225)            
{
  step2=2;       
  step1=step2;
}  
    
   void var_init(void)
    {
     crcshuju=0;
     describe=0;
     mingling=0;
     shu=0;
     shu1=0;
     shu2=0;
     shuju=0;
     Dshuju=0;
     jiaodu=0;
     sudu=0;
     jiandaoshuju=0;
     s5=0;
     s6=0;
     s5tem=1;
     s6tem=1;
     s7tem=0;
     s8tem=0;
     s7tem1=0;
     s8tem1=0;
     s7tem2=0;
     s8tem2=0;
     other=0;
     tiaoshiflag=0;
     maojinspeedold=10;
     a_lock1=0;
     b_lock1=0;
     a_lock=0;
     b_lock=0;
     Hdaowei1=0;
     zhenspeed1=1;
     flag6=1;
     HHmove=1;
     yu=0;
     yu1=0;
     halfyu=0;
     error=0;
     jiandaochaoshi=0;
     uartshu=0;
     spi=0;
     reshu=0;
     reshu1=0;
     BMMODE=0;
     BMTEST=0;
     //h=0;
     firsta1=0;
     positionaold=0;
     positionbold=0;
     positiona1=0;
     positionb1=0;
     position=0;
     position1=0;
     maxa=0;
     mina=255;
     maxb=0;
     minb=255;
     error21=0;
     error22=0;
     uartempty=0;
     firstona=0;
     firstonb=0;
     jiwei=0;
     HHmove1=0;
     chaoshi1=0;
     ZXS=6;
     
     hdposition=0;
     hdpositionold=0;
     h1flag=0;
     
     chuanxianflag=0;
     shangdian=0;
     zhenweiold=1;
     H4POS=0;
     buc=2;
     bcshuju=0;
     HHangle1=11;
     VATH=4;
     boardnum=0;
     banshuju=0;
     }     
void  decide_a_direct(void)             // motor a direct & stop estimate
{ 
  static u8 maf_f=0;
  if(adcxa<4)// arrive position在针高模式中断产生脉冲的时候会先查AD值,然后再调用这个函数
    {//adcxa是通过串口传递的针高值，通过查表获得表的值和取得的AD值得差的绝对值 
    	if(maf_f<2) 
    	  maf_f+=1;
        else
        {
          moveafinish=1;// set finish flag如果要求的针高和实际检测到的AD值相差小于4，需要设置停止标记
      	  h2=1;         // little current  
      	  maf_f=0;
       }
   }	                                           
  else
   {  
      maf_f=0;
      if(adcvaluea>posivaluea) // direct decide  
      { 
      	cw2=0;
       }         
      else 
      { 
      	cw2=1;
      }         
   }	
}

void  decide_b_direct(void)               // motor b direct & stop estimate
{
	static u8 mbf_f;
  if(adcxb<4)
  {
    if(mbf_f<2) 
        mbf_f+=1;
    else
      {
       movebfinish=1;
       h1=1;                              //little current
       mbf_f=0;
      } 
  }		
  else 
    { 
    	mbf_f=0;
      if(adcvalueb>posivalueb)  
      { 
      	cw1=0;
      }         
      else 
      { 
      	cw1=1;
      }         
    }
}     

void chaoshi_error(uchar i)                         // 超时 error
{
	if(i==1) 
	  error=(error | 0x0040);      
	else if(i==2) 
	  error=(error | 0x0080);  
}
// TIMERA0 中断, 主要产生 H/D 轴脉冲
//interrupt[TIMERA0_VECTOR] void Timer_A0 (void)         // timera0 interrupt for pulse output
#pragma vector=TIMERA0_VECTOR //在哪里触发中断？在pulse函数中启动中断                        
__interrupt void Timer_A0 (void)

{  
   if (mode==1)// H mode
   {
    if(uartshu<11)//在串口中断中接收完数据后就会调用pulse、pulse1~7，在这几个pulse函数中，就会对uartshu清零
    {
     if(spi==0)
     {
       spi=1;
       P2OUT&=0xf7;
       uartshu1=10-uartshu;//uartshu1不用赋初始值
       UARTSHUJU=(putdata1>>uartshu1)&0x01;
       if(UARTSHUJU==1)
       {
         P1OUT&=0xfd;
       }
       else
       {
         P1OUT|=0x02;
       }
       //CCR0=CCR0+100;
     }
     else//数据放到P1.2上去了，于是下面就通过P1.1产生DSP中断，让DSP去取数据
     {
       spi=0;
       uartshu=uartshu+1;
       //CCR0=CCR0+150;
       P1OUT^=0x01;
     }
     CCR0=CCR0+150;
     if(uartshu==11)
     {
        CCR0=CCR0+1000;
     }
     }//结束if(uartshu<11)，什么时间uartshu变0呢？UART收到数据后，调用pulse函数，启动中断前清零。
    else
    {
     P2OUT|=0x08;
     P1OUT|=0x02;
   	//n1=n1-1;
   	//m=0;
   	HHmove=0;
   if((maojinspeed>50) && (maojinangle>422))
   {
   		H1quxian=Hquxian3[pointer5];
   }
   else if(maojinangle<=340)
   {
   		H1quxian=Hquxian4[pointer5];  //pjz20070122
   }
   else
   {
   		H1quxian=Hquxian2[pointer5];
   }
   H2v2=H1quxian*Hxs;
   v2=H2v2;
   CCR0=CCR0+v2;
   if (m1<maojinangle)
  {
	   P2OUT&=0xdf;  // pulse
	   pointer5=pointer5+1;
	   if(pointer5==AN)//AN是角度的一半，完成一半后，电机就需要降速，就是反过来取曲线数据
      {
       if(maojinangle<=340)
       {
       	pointer5=340-AN;
       }
       else
       {
       	pointer5=600-AN;//pjz20070117 pointer5=(600-AN)+1;
       }
     }            
   	m1=m1+1;
   	P1OUT^=0x01;
  }//角度已经走完成
   else
   { 
   	CCTL0 &= ~CCIE;
     	HHmove=1;//H轴完成标志
     	IE1 |= URXIE0;
     	reshu1=0;
     	n1=0;
     	duanjian=1;
     	if(maojinccw1==0)
     	{
     	  duanjian2=1; // 查断检
     	}
    }
   }
   }//结束H mode
  else if (mode==4)// D mode
  {
   if(uartshu<11)//开始调用pulse函数的时候uartshu初始化是0，而且在pulse函数中也赋值为0
     {
	     if(spi==0)//spi初始化是0
	     {
			     spi=1;//第二次中断的时候就走下面的else，用于产生中断
			     P2OUT&=0xf7;//p2.3变0；通知DSP信息，是接DSP的PC4，PC4低电平，DSP进入数据传递模式
			     uartshu1=10-uartshu;
			     UARTSHUJU=(putdata1>>uartshu1)&0x01;
			     if(UARTSHUJU==1)
			     {
			     	P1OUT&=0xfd;
			     }
			     else
			     {
			     	P1OUT|=0x02;
			     }
	     }
	     else//
	     {
		     spi=0;
		     uartshu=uartshu+1;
		     P1OUT^=0x01;//DSP的外部中断，DSP中断处理程序中去读P1.1的值，于是把角度和方向传递给DSP
	     }
     CCR0=CCR0+150;
     if(uartshu==11)//最后一位的时候就到11
     {
     		CCR0=CCR0+2000;
     }
     }//结束if(uartshu<11)
    else//大于11产生的中断，下面的中断就是产生D轴的脉冲
    {
     P2OUT|=0x08;//p2.3变1；通知DSP信息，是接DSP的PC4，PC4高电平，DSP进入数据传递模式
     P1OUT|=0x02;//p1.1变高，表示产生脉冲
   
     HHmove=0;
    
     H1quxian=Dquxian1[pointer5];                                  //normal mode
     Dv2=H1quxian*Dxs;//速度体现在Dxs中
     v2=Dv2;
     CCR0=CCR0+v2;//为下一次中断作准备，所以曲线、速度是为timer提供中断延时，
     if (m2<maojinangle)//提供有多少个脉冲，方向和角度已经从数据传递给DSP了，这里又通过脉冲告诉DSP，走多少个脉冲
     {//
			   pointer5=pointer5+1;
			   if(pointer5==AN)
			   {
       			pointer5=800-AN;//pjz20070117 pointer5=(600-AN)+1;AN是maojinangle的一半，升速走完一半后就反过来取曲线，减速
     			}            
			   m2=m2+1;
			   P1OUT^=0x01;                                                  //+
      }
		 else//经过下面后就不会再产生中断
		   { 
		   	CCTL0 &= ~CCIE;
		     	IE1 |= URXIE0;
		     	HHmove=1;//D轴完成标志
		     	reshu1=0;
		    }
    } 
  }
  else if (mode==3)// H PY mode
  {
   if(uartshu<11)
    {
     if(spi==0)
     {
	     spi=1;
	     P2OUT&=0xf7;
	     uartshu1=10-uartshu;
	     UARTSHUJU=(putdata1>>uartshu1)&0x01;
	     if(UARTSHUJU==1)
	     {
	     	P1OUT&=0xfd;
	     }
	     else
	     {
	     	P1OUT|=0x02;
	     }
     }
     else
     {
	     spi=0;
	     uartshu=uartshu+1;
	     //CCR0=CCR0+150;
	     P1OUT^=0x01;
     }
     CCR0=CCR0+100;
     if(uartshu==11)
     {
     	CCR0=CCR0+2000;
     }
   	}
    else
    {
     	P2OUT|=0x08;                                         //normal mode
   		v2=Hquxian1[pointer5]*PYxs;
   		CCR0=CCR0+v2;
   		//m=m+1;
		   if (m2<PYangle)
		   {
		   		if (PYcw==0x80)
				   {
					   P1OUT&=0xfd;
					   //P1OUT|=0x02;
					   //P2OUT|=0x20;
				   }                                               // pulse
				   else
				   {//P1OUT&=0xfd;
				     P1OUT|=0x02;
				    //P2OUT&=0xdf;
				    }// director
				   if (m2<AN4)
				   { 
					   pointer5=pointer5+1;
					   if(pointer5>59) 
					   		pointer5=59;
				   }
				   else if (m2>AN3) 
				   {
					   pointer5=pointer5-1;
					   if(pointer5>61) 
					   		pointer5=0;
				   }
				   m2=m2+1;
				   P1OUT^=0x01;
				   //P1OUT^=0x08;
				   //P1OUT^=0x01;                                                  //+
   		}//结束if (m2<PYangle)
   else
   { 
   		CCTL0 &= ~CCIE;
     	HHmove=1;
   }
   //v2=KV[pointer5]*V1;
   //CCR0=CCR0+v2;
    }//结束偏移的命令
  } 
 else if (mode==5) // huanse mode boardnum=0的时候换色模式，什么时候boardnum为0？主控没有发0xb4的命令所以boardnum始终是0
  {
   if(uartshu<11)
    {
     if(spi==0)
     {
	     spi=1;
	     P2OUT&=0xf7;
	     uartshu1=10-uartshu;
	     UARTSHUJU=(0x7fe>>uartshu1)&0x01;
	     if(UARTSHUJU==1)
	     {
	     	P1OUT&=0xfd;
	     }
	     else
	     {
	     	P1OUT|=0x02;
	     }
	     //CCR0=CCR0+100;
     }
     else
     {
	     spi=0;
	     uartshu=uartshu+1;
	     //CCR0=CCR0+150;
	     P1OUT^=0x01;
     }
     CCR0=CCR0+100;
     if(uartshu==11)
     {
     	CCR0=CCR0+2000;
     }
     }//结束if(uartshu<11)
     else
     {
     	P1OUT|=0x02;
      P2OUT|=0x08;
   //m=m+1;
   if(m4==0)
   {
    	m5=m5+1;
    	CCR0=CCR0+200*HHxs;
     if(m5<HHangle1)//HHangle1是主控传递过来的，应该是转动任意角度，然后再回到开始转动的角度
     {
     	P1OUT|=0x02;//P1.1是高 奇数头电机方向
      P2OUT|=0x20;//P2.5是高 偶电机方向
     	P1OUT^=0x01;//P1.0     A头电机脉冲
     	P1OUT^=0x08;//P1.3     B头电机脉冲
     }
     else if(m5>(HHangle1+2) && m5<(3*HHangle1+1))
     {
     	P1OUT&=0xfd;//P1.1是低
      P2OUT&=0xdf;//P2.5是低
      P1OUT^=0x01;
      P1OUT^=0x08;
     }
     else if(m5>(3*HHangle1+3) && m5<(5*HHangle1+2))
     {
     	P1OUT|=0x02;
      P2OUT|=0x20;
      P1OUT^=0x01;
      P1OUT^=0x08;
     }
     else if(m5>(5*HHangle1+4) && m5<(6*HHangle1+4))
     {
     	P1OUT&=0xfd;//
      P2OUT&=0xdf;
      P1OUT^=0x01;
      P1OUT^=0x08;
     }
     else if(m5>(6*HHangle1+6))//m5超过6针位的时候归零
     {
     	m4=1;//表示不能够晃环了，晃环过头了
      m5=0;
     }
   }//结束if(m4==0)
   else
   {
	   if (huanse==1)//换色
	   {
			   	AN3=Huanseangle-68;
			    AN4=60;
			   if(Huanseangle<120)
			   {
			   	AN3=Huanseangle/2;
			    AN4=AN3;
			   }                                                 //normal mode
			   if (m2<Huanseangle)
			   {
			   		v2=HSquxian1[pointer5]*HSxs;
			   		CCR0=CCR0+v2;
				   if (Huansecw==0x80)
				   {
					   P1OUT&=0xfd;
				   }                                               // pulse
				   else
				   {
				   	//P1OUT&=0xfd;
				    P1OUT|=0x02;
				    //P2OUT|=0x20;
				    }
			                                                   // director
			   if (m2<AN4)
			   { 
				   pointer5=pointer5+1;
				   if(pointer5>59) 
				   		pointer5=59;
			   }
			   
			   else if (m2>AN3) 
			   {
				   pointer5=pointer5-1;
				   if(pointer5>61) 
				   		pointer5=0;
			   }
			  
			   m2=m2+1;
			   P1OUT^=0x01;
			   //P1OUT^=0x08;
			   //P1OUT^=0x01;  //+
		   }//结束if (m2<Huanseangle)
		   else
		     {
		     	if(m6==0)
		      {
		      	m5=m5+1;
		     		CCR0=CCR0+200*HHxs;
		     		if(m5>2 && m5<(HHangle1+2))
		     		{
		     			P1OUT|=0x02;
		      		//P2OUT|=0x20;
		      		P1OUT^=0x01;
		      		P1OUT^=0x08;
		      	}
		     		else if(m5>(HHangle1+4) && m5<(3*HHangle1+3))
		     		{
		     			P1OUT&=0xfd;
		      		//P2OUT&=0xdf;
		      		P1OUT^=0x01;
		      		P1OUT^=0x08;
		      	}
		     		else if(m5>(3*HHangle1+5) && m5<(5*HHangle1+4))
		     		{
		     			P1OUT|=0x02;
		      		//P2OUT|=0x20;
		      		P1OUT^=0x01;
		      		P1OUT^=0x08;
		      		}
		     		else if(m5>(5*HHangle1+6) && m5<(6*HHangle1+6))
		     		{
		     			P1OUT&=0xfd;
		      		P1OUT&=0xdf;
		      		P1OUT^=0x01;
		      		P1OUT^=0x08;
		      	}
		     		else if(m5>(6*HHangle1+8))
		     		{
		     			m6=1;
		     			CCTL0 &= ~CCIE;
		     			HHmove=1;
		     		}
		     	}//结束if(m6==0)
		    }//结束if (m2<Huanseangle)的else
   }//结束if (huanse==1)
   else//在晃环的pulse5函数中会将huanse变0
     { 
     	CCTL0 &= ~CCIE;
     	HHmove=1;
     }
   //v2=KV[pointer5]*V1;
   //CCR0=CCR0+v2;
   }//结束if(m4==0)的else
   }//结束if(uartshu<11)的else
  } 
  else if (mode==9) // huanse mode boardnum=0的时候换色
  {
   if(uartshu<11)
    {
     if(spi==0)
     {
     spi=1;
     P2OUT&=0xf7;
     uartshu1=10-uartshu;
     UARTSHUJU=(0x7fe>>uartshu1)&0x01;
     if(UARTSHUJU==1)
     {P1OUT&=0xfd;}
     else
     {P1OUT|=0x02;}
     //CCR0=CCR0+100;
     }
     else
     {
     spi=0;
     uartshu=uartshu+1;
     
     //CCR0=CCR0+150;
     P1OUT^=0x01;
     }
     CCR0=CCR0+100;
     if(uartshu==11)
     {CCR0=CCR0+2000;}
     }
     else
     {P1OUT|=0x02;
      P2OUT|=0x08;
   //m=m+1;
   if(m4==0)//进入换色、晃环、H/D轴测试的时候都是0
   {
    	m5=m5+1;
    	CCR0=CCR0+200*HHxs;
     if(m5<HHangle1)
     {
     	P1OUT|=0x02;
      P2OUT|=0x20;
     	P1OUT^=0x01;
     	P1OUT^=0x08;
     	}
     else if(m5>(HHangle1+2) && m5<(3*HHangle1+1))
     {
     	P1OUT&=0xfd;
      P2OUT&=0xdf;
      P1OUT^=0x01;
      P1OUT^=0x08;
      }
     else if(m5>(3*HHangle1+3) && m5<(4*HHangle1+3))
     {
     	P1OUT|=0x02;
      P2OUT|=0x20;
      P1OUT^=0x01;
      P1OUT^=0x08;
      }
     else if(m5>(4*HHangle1+5))
     {
     	m4=1;
      m5=0;
      }
   }//结束if(m4==0)
   else
   {
   if (huanse==1)
   {
	   	AN3=Huanseangle-68;
	    AN4=60;
	   if(Huanseangle<120)
	   {
	   	AN3=Huanseangle/2;
	    AN4=AN3;
	   }                                                 //normal mode
   
   if (m2<Huanseangle)
   {
   		v2=HSquxian1[pointer5]*HSxs;
   		CCR0=CCR0+v2;
   		if (Huansecw==0x80)
   		{
			   P1OUT&=0xfd;
			   //P1OUT|=0x02;
			   //P2OUT&=0xdf;
		   }                                               // pulse
   else
   {//P1OUT&=0xfd;
    P1OUT|=0x02;
    //P2OUT|=0x20;
    }
                                                   // director
   if (m2<AN4)
   { 
   		pointer5=pointer5+1;
   		if(pointer5>59) 
   			pointer5=59;
   }
   
   else if (m2>AN3) 
   {
   
	   pointer5=pointer5-1;
	   if(pointer5>61) 
	   		pointer5=0;
   }
  
   m2=m2+1;
   P1OUT^=0x01;
   //P1OUT^=0x08;
   //P1OUT^=0x01;                                                  //+
   }//结束if (m2<Huanseangle)
   else
     {
     	if(m6==0)
      {
      	m5=m5+1;
     		CCR0=CCR0+200*HHxs;
     		if(m5>2 && m5<(HHangle1+2))
     		{
     			P1OUT|=0x02;
      		//P2OUT|=0x20;
      		P1OUT^=0x01;
      		P1OUT^=0x08;
      	}
     else if(m5>(HHangle1+4) && m5<(3*HHangle1+3))
     {
	     	P1OUT&=0xfd;
	      //P2OUT&=0xdf;
	      P1OUT^=0x01;
	      P1OUT^=0x08;
      }
       else if(m5>(3*HHangle1+3) && m5<(4*HHangle1+3))
     {
     	P1OUT|=0x02;
      P2OUT|=0x20;
      P1OUT^=0x01;
      P1OUT^=0x08;
     }
       else if(m5>(4*HHangle1+5))
     {
     	m6=1;
      CCTL0 &= ~CCIE;
     	HHmove=1;
     }
     }//结束if(m6==0)
    }//结束if (m2<Huanseangle)的else
   }//结束if (huanse==1)
   else
     {
     	CCTL0 &= ~CCIE;
     	HHmove=1;
     }
   //v2=KV[pointer5]*V1;
   //CCR0=CCR0+v2;
   }//结束if(m4==0)的else
   }
   }
  else if (mode==2)  //  原点,穿线点mode
  {
   
     
   if (flag5<240)                                     // 延时
   {
   if(uartshu<11)
    {
     if(spi==0)
     {
     spi=1;
     P2OUT&=0xf7;
     uartshu1=10-uartshu;
     UARTSHUJU=(putdata1>>uartshu1)&0x01;
     if(UARTSHUJU==1)
     {P1OUT&=0xfd;}
     else
     {P1OUT|=0x02;}
     //CCR0=CCR0+100;
     }
     else
     {
     spi=0;
     uartshu=uartshu+1;
     
     //CCR0=CCR0+150;
     P1OUT^=0x01;
     }
     CCR0=CCR0+200;
     if(uartshu==11)
     {CCR0=CCR0+2000;}
     }
     
   else
   {
   
   P2OUT|=0x08;
   P1OUT|=0x02;
   
   
   flag5=flag5+1;
   //uartshu=0;
   TD=60000;
   Hdaowei=P2IN&0x01;
   Hdaowei1=P5IN&0x01;
   if((Hdaowei==0x01)&& (Hdaowei1==0x01))
   {Hdaoweitimes+=1;}
   if(Hdaoweitimes>3)
   {flag5=241;
    Hdaoweitimes=0;}
   
   CCR0=CCR0+TD;
   }
   }
   else
   {
    if(firsta1==0)                                 //
    {firsta1=1;
     uartshu=0;
     }
    if(uartshu<11)
    {
     if(spi==0)
     {
     spi=1;
     P2OUT&=0xf7;
     uartshu1=10-uartshu;
     UARTSHUJU=(putdata2>>uartshu1)&0x01;
     if(UARTSHUJU==1)
     {P1OUT&=0xfd;}
     else
     {P1OUT|=0x02;}
     //CCR0=CCR0+100;
     }
     else
     {
     spi=0;
     uartshu=uartshu+1;
     
     //CCR0=CCR0+150;
     P1OUT^=0x01;
     }
     CCR0=CCR0+200;
     if(uartshu==11)
     {CCR0=CCR0+2000;}
     }
     
   else
   {
   P2OUT|=0x08;
   P1OUT|=0x02;
   //P2OUT|=0x08;
   AN3=zhenangle-62;
   AN4=60;
   if(zhenangle<120)
   {AN3=zhenangle/2;
    AN4=AN3;}  //normal mode
   v2=Hquxian1[pointer5]*zhenxs;
   CCR0=CCR0+v2;
   //m=m+1;
   if (m2<zhenangle)
   {
                                // director
   if (m2<AN4)
   { 
   pointer5=pointer5+1;
   if(pointer5>59) pointer5=59;
   }                      
   else if (m2>AN3) 
   {
   
   pointer5=pointer5-1;
   if(pointer5>61) pointer5=0;
   }
  
   m2=m2+1;
   P1OUT^=0x01;
   //P1OUT^=0x08;
   //P1OUT^=0x01; //+
   }
   else
   { CCTL0 &= ~CCIE;
     HHmove=1;
    
     }
   //v2=KV[pointer5]*V1;
   //CCR0=CCR0+v2;
   }
   } 
   }
    else if (mode==6)//  test
  {
  
    if(uartshu<11)
    {
     if(spi==0)
     {
     spi=1;
     P2OUT&=0xf7;
     uartshu1=10-uartshu;
     UARTSHUJU=(putdata1>>uartshu1)&0x01;
     if(UARTSHUJU==1)
     {P1OUT&=0xfd;}
     else
     {P1OUT|=0x02;}
     //CCR0=CCR0+100;
     }
     else
     {
     spi=0;
     uartshu=uartshu+1;
     
     //CCR0=CCR0+150;
     P1OUT^=0x01;
     }
     CCR0=CCR0+200;
     if(uartshu==11)
     {CCR0=CCR0+2000;}
     }
     
     else
      {
   
       P2OUT|=0x08;
       P1OUT|=0x02;
      
       uartshu=0;
       CCTL0 &= ~CCIE;
      }
    }
   else if(mode==7)
   {
       
   if(uartshu<11)
    {
     if(spi==0)
     {
     spi=1;
     P2OUT&=0xf7;
     uartshu1=10-uartshu;
     UARTSHUJU=(putdata1>>uartshu1)&0x01;
     if(UARTSHUJU==1)
     {P1OUT&=0xfd;}
     else
     {P1OUT|=0x02;}
     //CCR0=CCR0+100;
     }
     else
     {
     spi=0;
     uartshu=uartshu+1;
     
     //CCR0=CCR0+150;
     P1OUT^=0x01;
     }
     CCR0=CCR0+200;
     if(uartshu==11)
     {CCR0=CCR0+2000;}
     }
     
   else
   {
   
   P2OUT|=0x08;
   P1OUT|=0x02;
   CCTL0 &= ~CCIE;
     HHmove=1;
    }
    }
    
    
  else if (mode==8)// huanse mode 电机开环测试
  {
   if(uartshu<11)
    {
     if(spi==0)
     {
     spi=1;
     P2OUT&=0xf7;
     uartshu1=10-uartshu;
     UARTSHUJU=(0x7fe>>uartshu1)&0x01;
     if(UARTSHUJU==1)
     {P1OUT&=0xfd;}
     else
     {P1OUT|=0x02;}
     //CCR0=CCR0+100;
     }
     else
     {
     spi=0;
     uartshu=uartshu+1;
     
     //CCR0=CCR0+150;
     P1OUT^=0x01;
     }
     CCR0=CCR0+100;
     if(uartshu==11)
     {CCR0=CCR0+2000;}
     }
     else
     {P1OUT|=0x02;
      P2OUT|=0x08;
   //m=m+1;
  
   
    AN3=Huanseangle-68;
    AN4=60;
    if(Huanseangle<120)
   {AN3=Huanseangle/2;
    AN4=AN3;}                                                 //normal mode
   
   if (m2<Huanseangle)
   {
   v2=HSquxian1[pointer5]*HSxs;
   CCR0=CCR0+v2;
   if (Huansecw==0x80)
   {
   P1OUT&=0xfd;
   //P1OUT|=0x02;
   //P2OUT&=0xdf;
   }                                               // pulse
   else
   {//P1OUT&=0xfd;
    P1OUT|=0x02;
    //P2OUT|=0x20;
    }
                                                   // director
   if (m2<AN4)
   { 
   pointer5=pointer5+1;
   if(pointer5>59) pointer5=59;
   }
   
   else if (m2>AN3) 
   {
   
   pointer5=pointer5-1;
   if(pointer5>61) pointer5=0;
   }
  
   m2=m2+1;
   P1OUT^=0x01;
   //P1OUT^=0x08;
   //P1OUT^=0x01;                                                  //+
   
   
   }
   else
     { CCTL0 &= ~CCIE;
     HHmove=1;
     }
   //v2=KV[pointer5]*V1;
   //CCR0=CCR0+v2;
   }
   
   }
 }
 
 // TimerA1 中断, 主要控制针高,剪刀电机动作  

//interrupt[TIMERA1_VECTOR] void Timer_A1 (void)   // timera interrupt ( for motor a,b speed)

#pragma vector=TIMERA1_VECTOR               
__interrupt void Timer_A1 (void)

{static u16 time;
 
 switch( TAIV )
 { 
   case  2:                                                // ccr1 interrupt                                   
    { 
     if (jitou==1)                                         // zhen gao mode
     {
      if(jitoutest==0)
      {
       adcvaluea=ADC12MEM[4]>>2;
       adcvalueb=ADC12MEM[5]>>2;
       adcxa=abs(posivaluea-adcvaluea);                    // calculate distance 
       adcxb=abs(posivalueb-adcvalueb);
       //P4OUT|=0x80;
       if(pointer3<37) 
         pointer3+=1;                        // quxian
       if(((adcxa<11) &&(moveafinish==0)) || ((adcxb<11)&& (movebfinish==0)))
         { 
           if(pointer3>2) 
             pointer3-=2;
         }
         //pointer3=36;
         
         CCR1 =CCR1+V_VALUE[pointer3];                    // Add Offset to CCR1
         if (moveafinish==0)                               // a motor active
            {   
              decide_a_direct();                           // decide direct
              if (moveafinish==0)
            {  h2=0;                                       // big current 
              //quxiana();
             if(cw2==0)                                    // +
                 {
                    pointer2=pointer2+step2;               // "+1", 16 microstep;"+2", 8 microstep
                    if (pointer2>63)
                       {
                         pointer2=0;
                        }
                }
             else if(cw2==1)                               // -
                  {
                      if (pointer2==0x00 || pointer2>100)
                          {
                            pointer2=64;
                           }
              pointer2=pointer2-step2; 
                   }
             }
      //P4OUT^=0x80;
            }
         if (movebfinish==0)                                // b motor active  
              {
               decide_b_direct();
               if (movebfinish==0)  
              { h1=0;
               //quxianb();
               if(cw1==0)
                   {
                    pointer1=pointer1+step1;                // "+1", 16 microstep;"+2", 8 microstep
                    if (pointer1>63) pointer1=0;
       
                   }
              else if(cw1==1)
                  {
                    if (pointer1==0x00 || pointer1>100) pointer1=64;
       
                    pointer1=pointer1-step1; 
                   }
               }
               }
               
            }
            
    if(jitoutest==1)
      {
         time=0;
         if(m9<needlehigh)
          {m9=m9+1;
         if(m9<needlehigh1)
         { pointer3=pointer3+1;
           if(pointer3>37) pointer3=37;
         }
         else if(m9>needlehigh2)
         {pointer3=pointer3-1;
         if((pointer3<1) && (pointer3>100)) pointer3=0;
         } 
         zhenspeed=(V_VALUE[pointer3]*zhenspeed1)/8;
         CCR1 =CCR1+zhenspeed;                    // Add Offset to CCR1
         if (moveafinish==0)                               // a motor active
            { 
            
              cw2=cwneedlehigh;
              
              h2=0;                                       // big current 
              //quxiana();
             if(cw2==0)                                    // +
                 {
                    pointer2=pointer2+step2;               // "+1", 16 microstep;"+2", 8 microstep
                    if (pointer2>63)
                       {
                         pointer2=0;
                        }
                }
             else                               // -
                  {
                      if (pointer2==0x00 || pointer2>100)
                          {
                            pointer2=64;
                           }
                      pointer2=pointer2-step2; 
                   }
             
      
            }
           
         if (movebfinish==0)                                // b motor active  
              {
              
               h1=0;
               cw1=cwneedlehigh;
               //quxianb();
               if(cw1==0)
                   {
                    pointer1=pointer1+step1;                // "+1", 16 microstep;"+2", 8 microstep
                    if (pointer1>63) pointer1=0;
       
                   }
              else 
                  {
                    if (pointer1==0x00 || pointer1>100) pointer1=64;
       
                    pointer1=pointer1-step1; 
                   }
               
               }
               
            }
         else
         {moveafinish=1;
          movebfinish=1;
          h1=1;
          h2=1;
          }   
           }
          }
       
        else if (jianxian==1)                                           // jianxian mode
       { 
       if(jiejin==0)
       {
        if(jiejintimes<3)
        {s5=P2IN&0x40;                                                  //
         s6=P2IN&0x80;
         jiejintimes+=1;
         if (s5==0x40) daoweib1+=1;                                          // at position?
        
         if (s6==0x80) daoweia1+=1;
         }
         else
        {if(daoweia1>1) daoweia=1;
         else daoweia=0;
         if(daoweib1>1) daoweib=1;
         else daoweib=0;
         jiejintimes=0;
         jiejin=1;
         daoweia1=0;
         daoweib1=0;}
       
        if (jiantest==1)
       {daoweia=1;
        daoweib=1;
        jiejin=1;}
        }
        else
        {
        
         
        if(huiwei==1)
        {
         s5=P2IN&0x40;                                                  //
         s6=P2IN&0x80;
         
         if (s5==0x40) daoweib1+=1;                                          // at position?
          if(daoweib1>4) daoweib=1;
         if (s6==0x80) daoweia1+=1;
          if(daoweia1>4) daoweia=1;
         if (jiantest==1)
           {daoweia=1;
            daoweib=1;
           }
      if (((daoweia==0) && (moveafinish==0)) || ((daoweib==0) && (movebfinish==0)))                                 // 回位置先
         {
         chaoshi1=chaoshi1+1;
        if ((daoweia==0 )&& (moveafinish==0))                                    
          { h2=0;
            pointer4=20;
            if (pointer2==0x00 || pointer2>100) pointer2=64;
       
            pointer2=pointer2-step2;
           }
         
         if ((daoweib==0 )&& (movebfinish==0))
          {   h1=0;
            pointer4=20;
            if (pointer1==0x00 || pointer1>100) pointer1=64;
    
                pointer1=pointer1-step1;
           }
          if(chaoshi1>1600)
          { chaoshi1=0;
            if((daoweia==0 )&& (moveafinish==0))                                    
             { h2=1;
               moveafinish=1;
               chaoshi_error(1);
              }
             if((daoweib==0 )&& (movebfinish==0))                                    
             { h1=1;
               movebfinish=1;
               chaoshi_error(2);
              }
          }
          }
          
         if (((daoweia==1) || (moveafinish==1)) && ((daoweib==1) || (movebfinish==1)))                                   
             {
              if(a_lock)
              {moveafinish=1;
               h2=1;}
              if(b_lock)
              {movebfinish=1;
               h1=1;}
              daoweia1=0;
              daoweib1=0;
              huiwei=0;
             }
          
          }
          else
          {   
          if (halfjian==1)
         { 
           
           if ((( daoweia==1 )&&( moveafinish==0)) || ((daoweib==1) && ( movebfinish==0)))                                 // 在位置
         { jiandaochaoshi+=1;
        if (( daoweia==1 )&& (moveafinish==0))                                    
          { h2=0;
            pointer4=20;
            
            pointer2=pointer2+step2;
            if (pointer2>63) pointer2=0;
           }
         
         if ((daoweib==1 )&& (movebfinish==0)) 
           {   h1=0;
              pointer4=20;
            
              pointer1=pointer1+step1;
              if (pointer1>63) pointer1=0;
                
            }
         s5=P2IN&0x40;                                                  //
         s6=P2IN&0x80;
         
         if (s5==0) daoweib1+=1;                                          // at position?
          if(daoweib1>2) daoweib=0;
         if (s6==0) daoweia1+=1;
          if(daoweia1>2) daoweia=0;
          if(jiandaochaoshi>300)
          {
           if((moveafinish==0) && (daoweia==1))
           {moveafinish=1;
           chaoshi_error(1);}
           if((movebfinish==0) && (daoweib==1))
           {movebfinish=1;
           chaoshi_error(2);}
           jiandaochaoshi=0;
           daoweia1=0;
           daoweib1=0;
           }
           //daoweia=0;
           //daoweib=0;}}
          if ((( daoweia==0 )||( moveafinish==1 )) && ((daoweib==0) || ( movebfinish==1)))
          {pointer4=0;
           jiandaochaoshi=0;}
          }
          else
          {
           if (Ta2<halfanglejian)                            // 正转 ？ 步
          { Ta2=Ta2+1;
          
          if (moveafinish==0)                                // motor a active and head unlock
            {  h2=0;
            pointer2=pointer2+step2;                         // "+1", 16 microstep;"+2", 8 microstep
            if (pointer2>63) pointer2=0;
            }
          if (movebfinish==0)                                // motor b active and head unlock
           {  h1=0;
            pointer1=pointer1+step1;                         // "+1", 16 microstep;"+2", 8 microstep
            if (pointer1>63) pointer1=0;
            }
           if (Ta2<37)                                       // quxian
            {
           pointer4=pointer4+1;
            }
           else if (Ta2>halfanglejian2) 
            {
           pointer4=pointer4-1;
            }
          }
          
          else 
          { 
           
           h2=1;
           h1=1;
           daoweia1=0;
           daoweib1=0;
           moveafinish=1;
           
           movebfinish=1;
            
          }
         }
         }
         
         else if (jian==1)
         {
         
          
           if ((( daoweia==1 )&&( moveafinish==0 )) ||((daoweib==1) && ( movebfinish==0)))                                 // 在位置
         {
         jiandaochaoshi+=1;
        if (( daoweia==1 )&& (moveafinish==0))                                   
          { h2=0;
            pointer4=20;
            
            pointer2=pointer2+step2;
            if (pointer2>63) pointer2=0;
           }
         
         if ((daoweib==1 )&& (movebfinish==0))
           {   h1=0;
              pointer4=20;
            
              pointer1=pointer1+step1;
              if (pointer1>63) pointer1=0;
                
            }
         s5=P2IN&0x40;                                                  //
         s6=P2IN&0x80;
         
         if (s5==0) daoweib1+=1;                                          // at position?
          if(daoweib1>2) daoweib=0;
         if (s6==0) daoweia1+=1;
          if(daoweia1>2) daoweia=0;
          if(jiandaochaoshi>300)
          {
           if((moveafinish==0) && (daoweia==1))
           {moveafinish=1;
           chaoshi_error(1);}
           if((movebfinish==0) && (daoweib==1))
           {movebfinish=1;
           chaoshi_error(2);}
           jiandaochaoshi=0;
           daoweia1=0;
           daoweib1=0;
           }
          if ((( daoweia==0 )||( moveafinish==1 )) && ((daoweib==0) || ( movebfinish==1)))
          {pointer4=0;
          jiandaochaoshi=0;}
          }
          else
          {
          if (Ta2<anglejian)                                                // 正转 ？ 步
          { Ta2=Ta2+1;
          
          if (moveafinish==0)                               // motor a active and head unlock
           {  h2=0;
            pointer2=pointer2+step2;                         // "+1", 16 microstep;"+2", 8 microstep
            if (pointer2>63) pointer2=0;
           }
          if (movebfinish==0)                                // motor b active and head unlock
           {  h1=0;
            pointer1=pointer1+step1;                         // "+1", 16 microstep;"+2", 8 microstep
            if (pointer1>63) pointer1=0;
           }
           if (Ta2<37)                                       // quxian
           {
           pointer4=pointer4+1;
           }
           else if (Ta2>anglejian2) 
           {
           pointer4=pointer4-1;
           }
          }
           else                                              // 中间停顿 ?
           {
            if (Ta3<200) 
            {Ta3=Ta3+1;
            if (jiantest==0)
            {
            if (Ta3==1)
            {Ta4=0;
             s511=0;
             s611=0;}
            if (Ta3<4)
            { 
                                                             // 没转，报超时 
            s5=P2IN&0x80;                                    
            s6=P2IN&0x40;
            if (s5==0x80) s511=s511+1;
            else s511=0;
            if (s6==0x40) s611=s611+1;
            else s611=0;
           
            if ((s511>2) && (moveafinish==0))
            {
            chaoshi_error(1);
            moveafinish=1;}
            if ((s611>2) && (movebfinish==0)) 
            {chaoshi_error(2);
            movebfinish=1;}
            }
            }
            
            h1=1;                                            // 小电流
            h2=1;
            }
            else 
            {
            
            if (Ta4<anglejian3)                                       // 返回
            { Ta4=Ta4+1;
            if (moveafinish==0)
           { 
            h2=0;                                                    // "+1", 16 microstep;"+2", 8 microstep
            if (pointer2==0x00 || pointer2>100) pointer2=64;
             pointer2=pointer2-step2; 
           }
           if (movebfinish==0)
           { 
             h1=0;
             if (pointer1==0x00 || pointer1>100) pointer1=64;
            pointer1=pointer1-step1; 
           }    
            if (Ta4<37) 
            {
            pointer4=pointer4+1;
            }
            else if (Ta4>anglejian4)
            { 
            pointer4=pointer4-1;
            }
            }
            else
             {
             h2=1;
             h1=1;
             
         s5=P2IN&0x40;                                                  //
         s6=P2IN&0x80;
         
         if (s5==0x40) daoweib=1;                                          // at position?
          
         if (s6==0x80) daoweia=1;
          
           
           if (daoweia==1) 
           {
           daoweia1=0;
            moveafinish=1;}
           if (daoweib==1)
           {
            daoweib1=0;
            movebfinish=1;}
            
             }
           }
         }

        }
        }
         
            else
            {
              if(daoweia==1)
              {h2=1;
               moveafinish=1;
               daoweia1=0;}
               if(daoweib==1)
               {h1=1;
               movebfinish=1;
               daoweib=0;}
             }
        }
        }
         CCR1 =CCR1+(VATH*V_VALUE[pointer4])/4;
         }
         
     
         
          if(moveafinish & movebfinish)   
          {CCTL1 &= ~CCIE;   // 都到位 关中断
          IE1 |= URXIE0;}
          //P4OUT&=0x7f;
          break;               
         }
         
 
 case  4:                                                   // 超时判断
 {  
   if(moveafinish & movebfinish)   
      {  CCTL2 &= ~CCIE;
         IE1 |= URXIE0;
         time=0;
       }
   else   
   {
            CCR2 =CCR2+30000;
            if(time<500) time+=1;                                //06.6.24 modify   增加超时判断时间
            else {
                  if(moveafinish==0)  
                     {  chaoshi_error(1);
                        moveafinish=1;
                        daoweia1=0;
                        h2=1;}	
                  if(movebfinish==0)
                     { chaoshi_error(2);	
                       movebfinish=1;
                       daoweib1=0;
                       h1=1;}
                 
                  CCTL2 &= ~CCIE;
                  IE1 |= URXIE0;
                  time=0;
                 }
           }
           break;
  }       //case   4
 case 10:   break;  
 }         //switch      
 
}  //tima
 // 针高,剪刀电机PWM 计算函数                                                  
 // pwm caculate program  ( p arithmetic)
 void pwmc(void)
 {
        //P1OUT ^= 0x01;
        if (CURRENTVALUE1>=126)                        // current is +
         {
           if (ADDATAH>CURRENTVALUE1)                  // ad value > 
            {
              E=ADDATAH-CURRENTVALUE1;                 // calculate error
              PWMS1=100-P*E;                           // calculate pwm value  
               if (PWMS1<3 || PWMS1>250 ) 
                 PWMS1=3;
             }           
            else            
              {            
               E=CURRENTVALUE1-ADDATAH;          
               PWMS1=100+P*E;
               if (PWMS1>197 ){PWMS1=197;}                   
               }
            }
         else                                        // CURRENT IS -
           {  
             if (ADDATAH<CURRENTVALUE1)         
                {
                 E=CURRENTVALUE1-ADDATAH;           
                 PWMS1=100+P*E;
                 if (PWMS1>197) {PWMS1=197;}            
                }        
              else            
                {
                  E=ADDATAH-CURRENTVALUE1;          
                  PWMS1=100-P*E;
                  if ( PWMS1<3 || PWMS1>250) {PWMS1=3;}            
                }
            }
            //P1OUT ^= 0x01;
 }
// 机头灯控制函数
void lbg(void)
{
//P1OUT &=0x7f;   //亮  绿 灯 b head
P1OUT&=0x7f;
}
void lbr(void)
{
//P1OUT &=0xbf;   //亮红灯 b head
P1OUT&=0xbf;
}

void lag(void)
{
//P1OUT &=0xdf;   //亮绿灯 a head
P1OUT&=0xdf;
}
void lar(void)
{
//P1OUT &=0xef;   //亮红灯 a head
P1OUT&=0xef;
}
void gal(void)       //关a灯
{
//PORTD=PORTD|0x30;   // a head
PORTD=PORTD|0x30;
}
void gbl(void)      //关b灯
{
//PORTD=PORTD|0xc0;   // b head
PORTD=PORTD|0xc0;
}


void error2(void)         //断检a
{ //gal();
  //lar();              //亮红灯 a head
  error=error | 0x0002;
  a_buxiu=1;
}
void error3(void)         //断检b
{ //gbl();
  //lbr();              //亮红灯 b head 
  error=error | 0x0004;
  b_buxiu=1;         //  置b补绣
}
void error4(void)        // 断检a,b
{//gal();
 //gbl();
 //lar();
 //lbr();
 error=error | 0x0400;
 a_buxiu=1;
 b_buxiu=1;
 }
void error5(void)   //a head oushu head
{error=error | 0x0100;
}
void error6(void)   //b head jishu head
{error=error | 0x0200;
}

// 机器起动函数 -- 置相关标志, 灯闪烁
void start(uchar a )    // when a==3 machine is from stop to run,for three swith duan jian
{  uchar i;             //      a==2 dian dong 
   //startdo=1;
   shandeng=0;
   gal();
   gbl();
   if(a==3)
    {
      for(i=0;i<3;i++)
         {//startdo=1;
          lar();
          lbr();
          delay(1000);
          gal();
          gbl();
          delay(1000);
		  }
    }
   if(a==2) 	  
    { for(i=0;i<2;i++)             // 闪灯2下
        { lar();
          lbr();
          delay(1000);
          gal();
          gbl();
          delay(1000);
		}  
	 } 	
   if((a_lock==0)&&(a_lock1==0)) lag();
   if((b_lock==0)&&(b_lock1==0)) lbg();		
	
}

//  停车函数    置相关状态
void stop(void)    // when machine is from run to stop,for three swith duan jian
{  
  startdo=0;
}

//  断检函数   接近开关式断检
void zero_pulse(void)  // duanjian     
{static uchar threetimes,duanxianou,duanxianji,p4tem=0,p4tem1=1;
 
 //errortime=0;
 p4tem=P4IN;
 delay(2);
 p4tem1=P4IN;
 while(p4tem!=p4tem1)
 {p4tem=P4IN;
 delay(2);
 p4tem1=P4IN;}
 /*
 if(duanjian2==1)
 {duanjian1=0;
  duanjian2=0;}
  */
  duanjian=0;
  threetimes+=1;
 if(((p4tem & 0x40)) && (a_lock==0) )
    {if(buxiu_flage)
       {if(a_buxiu) duanxianou+=1;}
    else duanxianou+=1;               // error2() ou shu head duanxian a
    }
 if(((p4tem & 0x80)) &&( b_lock==0)) // error3()ji shu head duanxian b
    {if(buxiu_flage)
       {if(b_buxiu) duanxianji+=1;}
     else duanxianji+=1; 
    }
 if(threetimes>=3)                   // 3 times
   { threetimes=0;
      duanjian1=0;
     if(duanxianou==3) error2();
	 if(duanxianji==3) error3();
	 duanxianou=0;
	 duanxianji=0;
   }
  	
 }
//  串口发送函数
void putchar( uchar putdata)         // 发送子程
{
  static u8 putdata_double;
  P5OUT |=DE;                        // 发送 enable  
  //delay(1);  
 
  while ((IFG1 & UTXIFG0) == 0);          // USART0 TX buffer ready?
  //UTCTL0 |=TXWAKE;                        //ADDRESS ID =1
  TXBUF0 =putdata;
  putdata_double=putdata;
  while((0x1 & UTCTL0) == 0); 
  
  P5OUT ^=DE;   
 
}

//  H/D 轴脉冲产生函数 (绣作中动作)
void pulse(void)// pulse output
{ 
//HHmove1=0;
if (HH==0)// 环梭模式，这个数是在接收中断函数中已经设置好，然后在中断处理函数中调用pulse函数                                         
{
 
 n1=0;
 HHmove=0;
 IE1^=URXIE0;
 if(maojinangle1>200)
 {h1flag=1;}
 else
 {h1flag=0;}
 
  if(h1flag==1)
  {
  maojinccw1=0x80;
  maojinangle=400+(buc-2)*10;
  hdpositionold=hdposition;
  H4POS=H4POS+400+(buc-2)*10;
  if(H4POS>800)
  {H4POS=H4POS-1600;}
 if((maojinspeed>50) && (maojinangle>422))
   {HXS2=HXSA2[(maojinangle/4)-1];}
   else if(maojinangle<=340)
   {
       HXS2=HXSA3[(maojinangle/4)-1];
   }   
   else
   {
   HXS2=HXSA1[(maojinangle/4)-1];
   }
   if(HXS2>1190)
  {HXS2=1190;}
   //HXS2=42;
   AN=maojinangle/2;
  pointer5=0;
 
 Hxs=(55*HXS2)/(2*maojinspeed);
  }
  else
  {
  if(maojinccw==0)
 {
  hdposition=maojinangle1;}
  else
 {
  hdposition=400-maojinangle1;}
  
  if(hdposition>hdpositionold)
  {maojinangle2=hdposition-hdpositionold;
   if(maojinangle2>200)
   {maojinangle2=400-maojinangle2;
    if(maojinangle2>67)
    {maojinangle=maojinangle2;}
    else
    {maojinangle=400+maojinangle2;}
   }
   else
   {maojinangle=400-maojinangle2;}
   }
   else
   {
   maojinangle2=hdpositionold-hdposition;
   if(maojinangle2>200)
   {maojinangle=maojinangle2;
   }
   else
   { if(maojinangle2>67)
     {maojinangle=maojinangle2;}
     else
     {maojinangle=400+maojinangle2;}
   }
   }
   maojinccw1=0x00;
   maojinangle=maojinangle+(buc-2)*10;
   if(maojinangle>467)                      //  07.05.21
   {maojinangle=maojinangle-400;}           //
   hdpositionold=hdposition;
   
   H4POS=H4POS-maojinangle;
   if(H4POS<-800)
   {H4POS=H4POS+1600;}
   
  if((maojinspeed>50) && (maojinangle>422))
   {HXS2=HXSA2[(maojinangle/4)-1];}
   else if(maojinangle<=340)
   {
       HXS2=HXSA3[(maojinangle/4)-1];
   }   
   else
   {
   HXS2=HXSA1[(maojinangle/4)-1];
   }
   if(HXS2>1190)
  {HXS2=1190;}
   //HXS2=42;

   AN=maojinangle/2;
   
  pointer5=0;
 
 Hxs=(55*HXS2)/(2*maojinspeed);
 }
 
 m1=0;
 m=0;
 putdata1=((maojinccw1<<3)+maojinangle)^0x400;
 uartshu=0;
 //pointer5=0;
 mode=1;
 
}
else if (HH==1)//D
{
 HHmove=0;
 IE1^=URXIE0;
 if(maojinccw==0)
 {
  hdposition=maojinangle1*4;
 }
 else
 {
  hdposition=-4*maojinangle1;
 }
 angle2=hdposition-hdpositionold;
 if(angle2<0) 
 {
 		if(angle2<-800)
 			{
 				maojinangle=1600+angle2;
  			maojinccw1=0x80;
  		}
	  else
	  	{
	  		maojinangle=-angle2;
	  		maojinccw1=0x00;
	  	}
 	}
 else
 {
 	if(angle2>800)
 		{
		 	maojinangle=1600-angle2;
		  maojinccw1=0x00;
  	}
  else
  	{
		 maojinangle=angle2;
		 maojinccw1=0x80;
		 }
	}
 	hdpositionold=hdposition;//保留当前角度，为下一次
  DXS2=DXSA1[(maojinangle/4)-1];//DXSA1有200个
  if(boardnum==0)
   {
   	AN3=maojinangle/2;
   }
   else
   {
   	AN=maojinangle/2;
   }
  pointer5=0;
  Dxs=(45*DXS2)/(maojinspeed);
 if (Dxs>1200)
 {
 	Dxs=1200;
 }
 m2=0;
 pointer5=0;
 maojinspeedold=maojinspeed;
 pointer6=0;//maojinccw1=0x80或者0x00，左移3位，表示第11位是方向，
 putdata1=((maojinccw1<<3)+maojinangle)^0x400;//异或，异为1，同为0,与100,0000,0000异或表示剩下0xx，xxxx，xxxx的11位数据
 uartshu=0;
 mode=4;
 }//D轴处理结束
 CCR0=TAR+500;//表示过1500个时钟周期后产生Timer_A0中断。
 CCTL0 = CCIE+OUTMOD_4;                                // CCR0 interrupt enabled
}

// H 轴偏移45度函数
void pulse1(void)                                             // pulse output
{
 mode=3;
 HHmove=0;
 if(PYcw==0)
 {PYangle2=PYangle1;}
 else
 {PYangle2=-PYangle1;}
 
  PYangle3=PYangle2;
  //PYyu=(PYangle2*10+PYyu)%9;
  
 if(PYangle3<0) 
 {PYangle=-PYangle3;}
 else
 {PYangle=PYangle3;}
 
 
 //Huanseangle=(Huanseangle1*10)/9;
 PYxs=((420*20/PYspeed)*10)/(20+PYangle1);
 if (PYxs>300)
 {PYxs=300;}
  m2=0;
  AN3=PYangle-68;
  AN4=60;
   if(PYangle<120)
   {AN3=PYangle/2;
    AN4=AN3;}
 pointer6=0;
 H4POS=H4POS-50;
 if(H4POS<-800)
 {H4POS=1600+H4POS;}
 putdata1=((PYcw<<3)+PYangle)^0x400;
 uartshu=0;
 CCR0=TAR+500;
 CCTL0 = CCIE+OUTMOD_4; 
 }
 
 // 找原点函数
 void pulse2(void)                                             // pulse output
{
 //P2OUT&=0xf7;
 mode=2;
 HHmove=0;
 flag5=0;
 if(jianxian==1)
 {
 zhenangle2=((zhenwei-1)*150)%400;
 /*if(zhenangle2>=200)
 {zhenangle=400-zhenangle2;
  zhencw=0x00;}
  else
 {zhenangle=zhenangle2;
  zhencw=0x80;}
 */ 
  if(shangdian==0)
  {zhenweiold=zhenwei;
  shangdian=1;} 
   zhenangle=zhenangle2;
   zhencw=0x80;
   
  H4POS=H4POS+(zhenwei-1)*150;
  if(zhenweiold>3)
  {H4POS=H4POS-400;}
  if(H4POS>800)
  {H4POS=H4POS-1600;}
  else if(H4POS<-800)
  {H4POS=H4POS+1600;}
  zhenweiold=zhenwei;
  if(abs(H4POS)<40)
  {putdata1=0x7fc;}
  else if(H4POS>=40)
  {putdata1=0x7ff;}
  else
  {putdata1=0x7fd;}
  H4POS=0;
 zhenxs=2000/(20+zhenangle);
 if (zhenxs>300)
 {zhenxs=300;}
 chuanxianflag=0;
  //hdpositionold=50;
 }
 else if(jitou==1)
 { zhenangle=0;
   zhencw=0;
   zhenxs=300;
   if(abs(hdposition)<40)
   {putdata1=0x7fc;}
   else if(hdposition>=40)
   {putdata1=0x7ff;}
   else
   {putdata1=0x7fd;}
   hdposition=0;
   hdpositionold=0;}
  m2=0;
 pointer6=0;
 putdata2=((zhencw<<3)+zhenangle)^0x400;
 uartshu=0;
 firsta1=0;
 CCR0=TAR+500;
 CCTL0 = CCIE+OUTMOD_4; 
 }
 
 // 穿线点函数
 void pulse3(void)                                             // pulse output
{
 P2OUT&=0xf7;
 mode=2;
 HHmove=0;
 flag5=0;
 if(jianxian==1)
 {
 zhenangle2=(zhenwei*150+50)%400;
 if(zhenangle2>200)
 {zhenangle=400-zhenangle2;
  zhencw=0x00;}
  else
 {
 zhenangle=zhenangle2;
  zhencw=0x80;
 }
 
 zhenxs=3000/(20+zhenangle);
 if (zhenxs>300)
 {zhenxs=300;}
 //H4POS=200;
 chuanxianflag=1;
  //hdpositionold=250;
 }
 else if(jitou==1)
 { zhenangle=800;
   zhencw=0;
   zhenxs=12;
   hdpositionold=800;
   }
  m2=0;
 pointer6=0;
 putdata2=((zhencw<<3)+zhenangle)^0x400;
 uartshu=0;
 firsta1=0;
 CCR0=TAR+500;
 
 CCTL0 = CCIE+OUTMOD_4; 
 }
 
 // 换色函数
void pulse4(void)                                             // pulse output
{
 if(boardnum==0)
 {
 	mode=5;
 }
 else
 {
 	mode=9;
 }
 m4=0;
 m5=0;
 m6=0;
 huanse=1;
 HHmove=0;
 Huanseangle=(Huanseangle1*10)/9;
 HSxs=600/HSspeed;
 if (HSxs>400)
 {
 	HSxs=400;
 }
 m2=0;
 pointer6=0;
 CCR0=TAR+500;
 CCTL0 = CCIE+OUTMOD_4;
 uartshu=0; 
 } 
 
 // 晃环函数
void pulse5(void)                                             // pulse output
{

if(boardnum==0)
 {
 	mode=5;
 }
 else
 {
 	mode=9;
 }
 m6=0;
 m4=0;
 m5=0;
 huanse=0;
 HHmove=0;
 //Huanseangle=(Huanseangle1*10)/9;
 HHxs=900/HHspeed;
 if (HHxs>300)
 {
 	HHxs=300;
 }
  m2=0;
 pointer6=0;
 uartshu=0;
 CCR0=TAR+500;
 CCTL0 = CCIE+OUTMOD_4; 
 }
 
 // H/D 轴测试
 void pulse8(void) // pulse output
{
 mode=8;
 m6=0;
 m4=0;
 m5=0;
 
 HHmove=0;
 Huanseangle=(Huanseangle1*10);
 HSxs=900/HSspeed;
 if (HSxs>300)
 {
 	HSxs=300;
 }
  m2=0;
 pointer6=0;
 uartshu=0;
 CCR0=TAR+500;
 CCTL0 = CCIE+OUTMOD_4; 
 }
 
 // H/D轴上电
 void pulse6(void) // pulse output
{
 mode=6;
 
 //HHmove=0;
 //BMMODE=0;
 //pointer6=0;
 
 putdata1=0x7fb;
 CCR0=TAR+500;
 CCTL0 = CCIE+OUTMOD_4;
 uartshu=0; 
 } 
 
 void pulse7(void) // pulse output
{
 mode=7;
 
 HHmove=0;
 pointer6=0;
 
 if(((a_lock==1)||(a_lock1==1))&&((b_lock==1)||(b_lock1==1)))
 {
 	putdata1=0x7f8;
 }
 else if((a_lock==1)||(a_lock1==1))
 {
 	putdata1=0x7fa;
 }
 else if((b_lock=1)||(b_lock1==1))
 {
 	putdata1=0x7f9;
 }
 else
 {
 	putdata1=0x7f7;
 }
 CCR0=TAR+500;
 CCTL0 = CCIE+OUTMOD_4;
 uartshu=0; 
 } 

// 剪线函数
void jianxian1(uchar b)                       // jianxian  init
{ //static u16 halfyu=0;
  CCR1 =CCR1+V_VALUE[0];
  pointer4=0;
  chaoshi1=0;
  jiandaochaoshi=0;
  jiejin=0;
           anglejian=(anglejian1*400+yu1)/9;
           yu1=(anglejian1*400+yu1)%9;
           anglejian3=anglejian+70;
           anglejian2=anglejian-36;
           anglejian4=anglejian+4;
           
           halfanglejian=(halfanglejian1*400+halfyu)/9;
           halfyu=(halfanglejian1*400+halfyu)%9;
  
           halfanglejian2=halfanglejian-36;
           daoweia1=0;
           daoweib1=0;
  if (moveafinish==1)                   // jianxian a init
  {
  if (b==1 && a_lock1==0)
     {moveafinish=0;
     //if(a_lock)
     //{jian=0;
     // halfjian=0;
     // huiwei=1;}
      Ta2=0;
      Ta3=0;
      Ta4=0;
      CCTL1 = CCIE+OUTMOD_4;            // CCR1 interrupt enabled
      
      if (moveafinish==0)  
       { 
        h2=0;
       }
      }
   } 
   
   if (movebfinish==1)                  // jianxian a init
  {
  if (b==0 && b_lock1==0)
     {movebfinish=0;
    // if(b_lock)
    // {jian=0;
    // halfjian=0;
    // huiwei=1;}
      Ta2=0;
      Ta3=0;
      Ta4=0;
      CCTL1 = CCIE+OUTMOD_4;            // CCR1 interrupt enabled
      
      if (movebfinish==0)  
       { 
        h1=0;
        }
      }
   } 
   CCTL2 = CCIE+OUTMOD_4;
  }                                      

// 升针高函数
void move1(uchar a)                     // zhen gao init
{
  if(jitoutest==0)
  {
    CCR1 =CCR1+V_VALUE[0];
    pointer3=0;
    adcxa=abs(posivaluea-adcvaluea);
    adcxb=abs(posivalueb-adcvalueb);
    fflaga=0;
    fflagb=0;
    if((a==1) && (a_lock1==0))                               // zhen gao a init
   { 
     //pointer3=0;
     adcvalueaold=adcvaluea;
     //movafirst=0;
     //adcvaluea0=adcvaluea;            //运动前的初值。
     moveafinish=0;
     CCTL1 = CCIE+OUTMOD_4;             // CCR1 interrupt enabled
     decide_a_direct();
     if (moveafinish==0)  
       { //pointer2=pointer2;
        h2=0;
        }       
        //PORTC=PORTC | 0x10;//big current            
    }
    if((a==0) && (b_lock1==0))                               // zhen gao b init                              
    {
       //movbfirst=0;
       //adcvalueb0=adcvalueb;
       adcvaluebold=adcvalueb;
       movebfinish=0;
       CCTL1 = CCIE+OUTMOD_4;            // CCR1 interrupt enabled 
       decide_b_direct();
       if (movebfinish==0)    
       { //pointer1=pointer1;
         h1=0;      
       }
    }
    CCTL2 = CCIE+OUTMOD_4;            // CCR2 interrupt enabled
 }//结束 if(jitoutest==0)
 else
 {
    CCR1 =CCR1+V_VALUE[0];
    pointer3=0;
    needlehigh=needleangle*32;
    needlehigh1=37;
    needlehigh2=needlehigh-38;
    if(needlehigh<74)
    {needlehigh1=needlehigh/2;
     needlehigh2=needlehigh1;}
    m9=0;
    if(a_lock1==0)// zhen gao a init
     { 
       moveafinish=0;
       CCTL1 = CCIE+OUTMOD_4;
       h2=0;
     }
    if(b_lock1==0)
     {
       movebfinish=0;
       CCTL1 = CCIE+OUTMOD_4; // CCR1 interrupt enabled 
       h1=0;
     } 
  }
}

void error1(void) // 开关坏
{ 
  lar();          //亮ab红灯
  lbr();
  error=error | 0x0001;            // ooooooooooooooooo
  error=0;
}

// 机头开关处理函数
void switch_bitB(void)                  // 机头开关
{
	if((pa&0x3)==0x3)//pa=P3IN&0xf 
		{ 
		  error1();                        //开关B坏   
	  	  goto quit_s_b;
	        }

        if((pa&0x01))            // B头拨下位 ( 锁head b)
			{
			 posivalueb=posivalue[10];  
			 if(startdo==0) 
			 {
                            if (jitou==1)
                            {
                              jitoutest=0;
                              move1(0);           //停车则动
                            }
			 }
			 b_lock=1;
		         gbl();           //关B头红绿灯
			 b_buxiu=0;
			
			 }// 结束 B头拨下位 ( 锁head b)
		 
		 else if((pa&0x2))       //B头拨补绣
		   {
                      gbl();
		      lbr();	              //B red 灯
		      b_buxiu=1;
		      b_lock=0;
		   }     
		 else                     //正常
		    {     b_lock=0;
			  if(b_buxiu==0)
			    {
                              if((firstonb==1)&&(buxiu_flage==0))
                              {
                                posivalueb=posivalue[jiwei];
                                move1(0);
                              }
                               gbl();
                               if(b_lock1==0)
                               {
                                lbg();
                               }
			    } 
			
			}
        firstonb=1;    		
	quit_s_b:  ;	  
  }

void switch_bitA(void)                  // 机头开关
{

if((pa&0x0c)==0x0c)
{ error1();                        // 开关A坏
  goto quit_s_a; 	
}
		 
		 if((pa&0x04))           //A头拨下位
			{
			 posivaluea=posivalue[10];  
		         if(startdo==0) 
		         {
		         if (jitou==1)
		         {jitoutest=0;
		         move1(1);}      //停车则动
		        
		          }
		         
		      
		 
			  a_lock=1;
			  gal();	          //关A头红绿灯
			  a_buxiu=0;
			
			 }
		 else if((pa&0x8))       //A头拨补绣
		    {  gal(); 
		       lar();	          //A red 灯
		       a_buxiu=1;
		    } 	
		 else { a_lock=0;
		        if(a_buxiu==0)
		          {
		          if((firstona==1)&&(buxiu_flage==0))
		          { 
		          posivaluea=posivalue[jiwei];
		          move1(1);
		          }
		            gal();
		            if(a_lock1==0)
		            {
			        lag();}
				   }	
			
			 }  
    firstona=1;    		
	quit_s_a:  ;	  
  }

void switch_1(void)                  // 机头开关
{

		 if((pa&0x01))            // B头拨下位 ( 锁head b)
			{
			 
			 b_lock=1;
			 b_buxiu=0;
			
			 }
		 
		 else if((pa&0x2))       //B头拨补绣
		   {              
		    b_buxiu=1;
		    b_lock=0;
	
		   }     
		 else                     //正常
		    { b_lock=0;
			}	 
		   
		 if((pa&0x04))           //A头拨下位
			{
			 
			  a_lock=1;
			  a_buxiu=0;
			
			 }
		 else if((pa&0x8))       //A头拨补绣
		    {  	       
		       a_buxiu=1;
		    } 	
		 else { a_lock=0;
		       
			 }  
  
  }  



void test_switch(void)              // 判断开关
{
 static u8 pa_flage=0;
 pa=P3IN &0x0f; 
 delay(10);
 tem=P3IN &0x0f; 
 if(pa==tem) 
   { if(pa_flage==0) 
	   { pa_old=pa;
	     pa_flage=1;            //porta口第一次标志
	     switch_bitB();
	     switch_bitA(); 
	   }
     if(pa!=pa_old) 
	  {
	   if((pa&0x03)!=(pa_old&0x03))
	   {switch_bitB();}            //不同才处理	 
	   if((pa&0x0c)!=(pa_old&0x0c))
	   {switch_bitA();}
	   pa_old=pa;
      }
   }

}
  
void test_switch1(void)             // 快速判断开关
{
 pa=P3IN &0x0f; 
 if(pa!=pa_old) 
   {pa_old=pa;
    switch_bitB();              //不同才处理	 
    }
  

}

void JP_buxiuA(void)
{
 if((a_lock) || (a_lock1))
  {
  P2OUT&=0xf9;
  }
 else if(a_buxiu==1) 
  {
  P2OUT|=0x04;
  P2OUT&=0xfd;
  }
 else 
 {P2OUT|=0x02;
  P2OUT&=0xfb;
  }
 }
 
 void JP_buxiuB(void)
{
 if((b_lock) || (b_lock1))
  {
  P3OUT&=0x3f;
  }
 else if(b_buxiu==1) 
  {
  P3OUT|=0x80;
  P3OUT&=0xbf;
  }
 else 
 {P3OUT|=0x40;
  P3OUT&=0x7f;
  }
 }
 
  
//  CRC 校验函数
 uint table_crc(uchar *ptr,uchar len) 
{
U8 da;
crc=0;
//len=2;
while(len--!=0)
{
da=(U8) (crc/256); // 以8 位二进制数暂存CRC 的高8 位
crc<<=8; // 左移8 位

crc^=crc_ta[da^*ptr]; // 高字节和当前数据XOR 再查表
ptr++;
}
return(crc);
}
 // 串口接收中断 
 //  usart0 interrupt service routine
 //interrupt[UART0RX_VECTOR] void usart0_rx (void)
#pragma vector=UART0RX_VECTOR
__interrupt void usart0_ISR (void)
{
//_EINT();
 addressflag=U0RCTL;                                   // 地址位标志
 getchar1=RXBUF0;                                      // 缓存中取数
//lar();2号板地址1101 1011          机头公用地址            板地址              地址位有效
 if((((getchar1==0xdb) || (getchar1==headcodex))||(getchar1==headcode)) && ((addressflag&0x02)==2))// 板地址对？ 2.17
 {      addreffect=1;
        URCTL0=0x00;                                   // 数据允许
        senddata[0]=getchar1;                          // 存地址
        crcshuju=0;                                    // 初值
        shu=0;
        jtshuju=0;
        Hsshuju1=0;
        chuanshuju=0;
        yuanshuju=0;
        PYshuju=0;
        djshuju=0;
        djshuju1=0;
        swshuju=0;
        zhengaoshuju=0;
        jiandaoshuju=0;
        Dshuju=0;
        shuju=0;
        zhentestshuju=0;
        uarttestshuju=0;
        describe=1; 
        Hsshuju2=0;
        bcshuju=0;
        HHshuju1=0;
        jiandaoshuju1=0;
        banshuju=0;
       goto end_rx_isr;//第一个字节是地址，退出接收中断
 }
   if(addreffect==1)                                   // 地址对 
     { 
       if(((moveafinish & movebfinish) ==0) || (HHmove==0))// 5.19 电机在转报忙，退出
	      {  
	         URCTL0=URXWIE; // 从新开始收数,只允许地址                            
	         addreffect=0;                         
	         describe=0;
		 goto end_rx_isr;
	      }
		    
	  if(describe==1)// 收到描述符（描述符包括查询命令、数据、查询）
	  {
	   crcshuju=crcshuju+1;
	   if(crcshuju==1)
	     {
	     	senddata[1]=getchar1; // 描述符存入数组
	        data1=getchar1;
	     }
	    if ((data1<0xb0) && (data1>0x5f))// 命令
	    { 
	      if(crcshuju==2)// crc 高位，如果是命令，那么命令就只有一个字节，那么当crcshuju==2，表示已经开始收到第3个字节，是CRC的高位
	      {
	      	crc1=getchar1;
	        goto end_rx_isr;
              }
	      if(crcshuju==3) // crc 低位
	      {
	      	describe=0;
	       	crc2=getchar1;
	       	crc11=crc1<<8;
                crc3=crc11+crc2;
                table_crc(senddata,2);// 两位数据的crc计算
                if(crc3!=crc)         // crc 校验错
                {
           	  error|=0x1000;
                  addreffect=0;
                  URCTL0=URXWIE;
                  goto end_rx_isr;
                }
                else//CRC校验正确
                {
	      		getchar1=senddata[1];                         // 校验正确执行相应操作
	      		addreffect=0;
	      		URCTL0=URXWIE;
	      		if(getchar1==0x90)                                         // 起动
				      {
				       startdo=1;
				       shandeng=1;
				      goto end_rx_isr;
				      }
				    if(getchar1==0x91)                                         // 停止
				      {
				       	stop();
				      	goto end_rx_isr;
				      }
				      if(getchar1==0x92)                                         // 点动
				      {
				       shandeng=1;
				      goto end_rx_isr;
				      }
					    if(getchar1==0x93)                                         //0 wei
					    {
					    	atzero=1;
						  	goto end_rx_isr;
						  }	
					     if(getchar1==0x94)//no at zero主轴不在0位
					     {
					     	atzero=0;
						  	goto end_rx_isr;
						  }	
	      
				      if(getchar1==0x95)                                       // 补绣
				      {
				      	buxiu_flage=1;
					   		goto end_rx_isr;
					   	} 
				      if(getchar1==0x96)                                       // 补绣结束
				      {
				      	buxiu_flage=0;
							  a_buxiu=0;
							  b_buxiu=0;
					   		goto end_rx_isr;
					  	} 
				      if((getchar1==0x60) && jianxian==1)                      // 剪刀回位
				      {
					       huiwei=1;
					       jian=0;
					       halfjian=0;
					       
					       jianxian1(1);
					       jianxian1(0);
					      
					      goto end_rx_isr;
				      }
				      if((getchar1==0x61) && jianxian==1)                      // 半出剪刀
				      {
				       huiwei=1;
				       jian=0;
				       halfjian=1;
		           if(buxiu_flage)
		           {
		           	if(a_buxiu)
		           		{
		           			jianxian1(1);
		           		}
		            if(b_buxiu)
		           		{
		           			jianxian1(0);
		           		}
		           }
		          else
		          {
				         jianxian1(1);
				         jianxian1(0);
			        }
			      	goto end_rx_isr;
			      } 
	      
	      if((getchar1==0x62) && jianxian==1)                        // 剪线
	      {
	       huiwei=1;
	       jian=1;
	       halfjian=0;
         if((startdo==0) && (atzero==1)) 
	       {
	       	if(buxiu_flage)
           {
           		if(a_buxiu)
           			{
           				jianxian1(1);
           			}
            	if(b_buxiu)
           			{
           				jianxian1(0);
           			}
            }
            else
            {
	         		jianxian1(1);
	         		jianxian1(0);
	        	}
	      }
	      goto end_rx_isr;
	      }
	      
	      if(getchar1==0x63)// D H 回原点
	      {
	        pulse6();
	      
	      goto end_rx_isr;
	      }
	      if((getchar1==0x68)&&(jianxian==1))// H晃动
	      {
	        pulse5();
	      	goto end_rx_isr;
	      }
	      
	      if(getchar1==0x69)// 通知D,H开关状态
	      {
	        if(HHmove==1)
	        {
	        	pulse7();
	        }
	      	goto end_rx_isr;
	      }
	      if(getchar1==0x71)// 盘带绣回原点
	      { 
	      	goto end_rx_isr;
	      } 
	      
	      if((getchar1==0x73) && (jitou==1))//空命令，上机头
		    { 
			     goto end_rx_isr; 	 
        }      
	     
	    if((getchar1==0x74) && (jitou==1))
	       {
	       	if(moveafinish) 
	       		putchar(adcvaluea>>2); // 发送 a 针高ad
		     else 
		     		putchar(0x62);
				goto end_rx_isr;
		   }
	     if((getchar1==0x75) && (jitou==1)) //发送 b 针高ad
	       {
	       	if(movebfinish) 
	       		putchar(adcvalueb>>2);
		      else 
		        putchar(0x62);
					goto end_rx_isr;
	       }
	    
	    if((getchar1==0x76) && (jitou==1))// && a_lock1==0))      //发送 a 针位置，H轴换色
	       {if(moveafinish) 
	       {
	        
	        putchar(positiona1);
	        }                                
		  
		    else putchar(0x62);
			goto end_rx_isr;
	       }   
		  if((getchar1==0x77) && (jitou==1))// && b_lock1==0))    //发送 b 针位置
	       {if(movebfinish)                                       
	       {
	       
	        putchar(positionb1);
	        }                                
		  
		    else putchar(0x62);
			goto end_rx_isr;}
			
		   if((getchar1==0x7c) && (jitou==1))// && a_lock1==0))      //发送运转中 a针高最大值，主要用于测试 max
	       {if(moveafinish) 
	       {
	        
	        putchar(maxa-mina);
	        adcvaluea=ADC12MEM[4]>>2;
            //adcvalueb=ADC12MEM[5]>>2;
	        maxa=adcvaluea>>2;
	        mina=adcvaluea>>2;
	        }                                
		  
		    else putchar(0x62);
			goto end_rx_isr;
	       }   
		  if((getchar1==0x7d) && (jitou==1))// && b_lock1==0))    //发送 a针高最小值 min
	       {if(movebfinish)                                       
	       {
	       
	        putchar(maxb-minb);
	        adcvalueb=ADC12MEM[5]>>2;
	        maxb=adcvalueb>>2;
	        minb=adcvalueb>>2;
	        }                                
		  
		    else putchar(0x62);
			goto end_rx_isr;}
		   if((getchar1==0x7e) && (jitou==1))// && a_lock1==0))      //发送 b针高最大值
	       {
	        adcvaluea=ADC12MEM[4]>>2;
	        maxa=adcvaluea>>2;
	        mina=adcvaluea>>2;
	        adcvaluea=ADC12MEM[5]>>2;
	        maxb=adcvalueb>>2;
	        minb=adcvalueb>>2;
	        
			goto end_rx_isr;
	        }   
		  if((getchar1==0x7f) && (jitou==1))// && b_lock1==0))    //发送 b min
	       {if(movebfinish)                                       
	       {
	       
	        putchar(minb);
	        minb=255;
	        }                                
		  
		    else putchar(0x62);
			goto end_rx_isr;}
	    
		 	   
	    if((getchar1==0x7b) && (jitou==1)) //针高模式 清灯空走，灯由红变绿
	      {
	       gal();
		   gbl();
		   if((a_lock==0)&&(a_lock1==0))
		   {
		   lag();
		   }
		   if((b_lock==0)&&(b_lock1==0))
		   {
		   lbg();
		   }
		   goto end_rx_isr;
		   } 	    
		
		if((getchar1==0x78) && (jitou==1))// 调试模式                
	      {tiaoshiflag=1;
	       goto end_rx_isr;
		   } 
		   
		if((getchar1==0x79) && (jitou==1)) // 结束调试模式                 
	      {tiaoshiflag=0;
	       goto end_rx_isr;
		   }
		   
	
		
		if ((tiaoshiflag==1)&&(jitou==1))
		{   
		if(getchar1==0x97 )//b红灯
		{ 
		  gbl();
		  lbr();
		  goto end_rx_isr;
		 }
		 
		 if(getchar1==0x98 )//b绿灯
		{ 
		  gbl();
		  lbg();
		  goto end_rx_isr;
		 } 
		 
		 if(getchar1==0x99 )//b黄灯
		{ gbl();
		  lbr();
		  lbg();
		  goto end_rx_isr;
		 }  
		 
		  if(getchar1==0x9a )
		{ gal();
		  lar();
		  goto end_rx_isr;
		 }  
		 
		  if(getchar1==0x9b )
		{ gal();
		  lag();
		  goto end_rx_isr;
		 } 
		 
		  if(getchar1==0x9c )
		{ gal();
		  lar();
		  lag();
		  goto end_rx_isr;
		 } 
	      
	      if(getchar1==0x9d )//b 灭
		{ gbl();
		  
		  goto end_rx_isr;
		 }  
		 
		 if(getchar1==0x9e )
		{ gal();
		  
		  goto end_rx_isr;
		 } 
		 
		 if(getchar1==0x9f )//a,b 灭
		{ gal();
		  gbl();
		  goto end_rx_isr;
		 } 
	     goto end_rx_isr;
	     } 
	   }  
	  }
	  goto end_rx_isr;
	  }  
	    
	   //                           查询
	    if ((data1<0xd9) && (data1>0xc9))//查询
	    { 
	    if(crcshuju==2)
	      {crc1=getchar1;
	      goto end_rx_isr;}
	      if(crcshuju==3)
	      {describe=0;
	       crc2=getchar1;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,2);
           if(crc3!=crc)
           {error|=0x1000;
            addreffect=0;
            URCTL0=URXWIE;
            goto end_rx_isr;
           }
           else
           {
           
	      getchar1=senddata[1];
	      addreffect=0;
	      URCTL0=URXWIE;
	      if (getchar1==0xca)                                              // 查 D,H 到原点否
          {//P2OUT|=0x08;
          if(HHmove==0)                                                    // H or D 在转
	       { putchar(0x63);
	         goto end_rx_isr;
	       }
	       
          if((error&0x2000==0x2000)&&(error&0x4000==0x4000))
           {
           putchar(0x55);
           }
           
          if(error&0x2000==0x2000)
           {
           putchar(0x53);
           }
          
          if(error&0x4000==0x4000)
           {
           putchar(0x53);
           }
          else
          {
          	putchar(headcode);
          }
	       goto end_rx_isr;
	      }
	   
	   
	      if ((getchar1==0xcb) && (jianxian==1))                                // 查断线
	    
          {//zero_pulse();
            duanjian1=1;
            duanjian=1;
	        startdo=1;
	       goto end_rx_isr;
	      }
	      if (getchar1==0xcc)                                                   // 查接近开关1，2
	      { if((moveafinish & movebfinish) ==0)
	         {putchar(0x62);}
	        else
	        { s5=P2IN&0x40;
              //if (s5==0) daoweiatimes=daoweiatimes+1;                         //
              s6=P2IN&0x80;
	          if (s5==0x40) daoweib=1;                                          // at position?
               else daoweib=0;
               if (s6==0x80) daoweia=1;
              else daoweia=0;
	        if ((daoweia==1)&&(daoweib==1)) 
	        {putchar(headcode);}
	        else
	        { 
	         if((daoweib==0) && (daoweia==0)) 
	         {putchar(0x03);}
	         else if(daoweia==0) 
	        {putchar(0x01);}
	         else if(daoweib==0) 
	         {putchar(0x02);}
	         
	         }
	         }
	         goto end_rx_isr;}
	         
	       if ((getchar1==0xcd) && (jitou==1))                              // 上机头板查开关状态
	       { pa1=b_lock+(b_buxiu<<1)+(a_lock<<2)+(a_buxiu<<3);
	       
	         putchar(pa1);
	         goto end_rx_isr;}
	     
	      if (getchar1==0xce)                                               // 查询通讯状态
	     { if((moveafinish & movebfinish) ==0)                              // 5.19 电机在转报忙，退出
	      {  putchar(0x62);
	         goto end_rx_isr;
	      }
	       if(HHmove==0)                                                    // H or D 在转
	       { putchar(0x63);
	         goto end_rx_isr;
	       }
	        s7=P2IN&0x01;
            if((s7==0) && ((error & 0x2000)!=0x2000 ))
             {putchar(0x65);
             goto end_rx_isr;
             }
             
            s8=P5IN&0x01;
             if((s8==0) && ((error & 0x4000)!=0x4000 ))
             {putchar(0x65);
             goto end_rx_isr;
             }
              
	        if(error==0)                                // 没错误，回板地址  
		    {putchar(headcode);
			 goto end_rx_isr;
			 }
		    else {
		       
		        if(((error & 0x0002)==0x0002 ) || ((error & 0x0004)==0x0004))     //断线
				  { if((((error & 0x0002)==0x0002) && (a_lock1==0)) && (((error & 0x0004)==0x0004) && (b_lock1==0)))
				     {                                                             // a b
				      putchar(0x13);
				      error=0;
				      goto end_rx_isr;
				     }
				    else if(((error & 0x0002)==0x0002) && (a_lock1==0))             // a 断线                                  // 断线 a
				     {
				      putchar(0x11);
				      error=0;
				      goto end_rx_isr;
				      }
				    else if(((error & 0x0004)==0x0004) && (b_lock1==0))            // b 断线
				     {
				      putchar(0x12);
				      error=0;
				      goto end_rx_isr;
				      }
				    else
				      {;}
				   }
				   
				if(((error & 0x0100)==0x0100 ) || ((error & 0x0200)==0x0200))     // 针高异常
				  { if((((error & 0x0100)==0x0100) && (a_lock1==0)) && (((error & 0x0200)==0x0200) && (b_lock1==0)))
				     {                                                             // a b
				      putchar(0x06);
				      error=0;
				      goto end_rx_isr;
				     }
				    else if(((error & 0x0100)==0x0100) && (a_lock1==0))             // a ?                                 // 断线 a
				     {
				      putchar(0x04);
				      error=0;
				      goto end_rx_isr;
				      }
				    else if(((error & 0x0200)==0x0200) && (b_lock1==0))            // b 
				     {
				      putchar(0x05);
				      error=0;
				      goto end_rx_isr;
				      }
				    else
				      {;}
				   }
		
				if(((error & 0x0001)==0x0001 ) || ((error & 0x0008)==0x0008))     //开关坏
				  { if((((error & 0x0001)==0x0001) && (a_lock1==0)) && (((error & 0x0008)==0x0008) && (b_lock1==0)))
				     {                                                             // a b
				      putchar(0x23);
				      error=0;
				      goto end_rx_isr;
				     }
				    else if(((error & 0x0001)==0x0001) && (a_lock1==0))             // a ?                                 // 断线 a
				     {
				      putchar(0x21);
				      error=0;
				      goto end_rx_isr;
				      }
				    else if(((error & 0x0008)==0x0008) && (b_lock1==0))            // b 
				     {
				      putchar(0x22);
				      error=0;
				      goto end_rx_isr;
				      }
				    else
				      {;}
				   }
				
			    if(((error & 0x0010)==0x0010 ) || ((error & 0x0020)==0x0020))     //电机反转
				  { if((((error & 0x0010)==0x0010) && (a_lock1==0)) && (((error & 0x0020)==0x0020) && (b_lock1==0)))
				     {                                                             // a b
				      putchar(0x33);
				      error=0;
				      goto end_rx_isr;
				     }
				    else if(((error & 0x0010)==0x0010) && (a_lock1==0))             // a ?                                 // 断线 a
				     {
				      putchar(0x31);
				      error=0;
				      goto end_rx_isr;
				      }
				    else if(((error & 0x0020)==0x0020) && (b_lock1==0))            // b 
				     {
				      putchar(0x32);
				      error=0;
				      goto end_rx_isr;
				      }
				    else
				      {;}
				   }
			    if(((error & 0x0040)==0x0040 ) || ((error & 0x0080)==0x0080))     //电机超时
				  { if((((error & 0x0040)==0x0040) && (a_lock1==0)) && (((error & 0x0080)==0x0080) && (b_lock1==0)))
				     {                                                             // a b
				      putchar(0x43);
				      error=0;
				      goto end_rx_isr;
				     }
				    else if(((error & 0x0040)==0x0040) && (a_lock1==0))             // a ?                                 // 断线 a
				     {
				      putchar(0x041);
				      error=0;
				      goto end_rx_isr;
				      }
				    else if(((error & 0x0080)==0x0080) && (b_lock1==0))            // b 
				     {
				      putchar(0x42);
				      error=0;
				      goto end_rx_isr;
				      }
				    else
				      {;}
				   }
			    
				if((error & 0x1000)==0x1000)          // CRC数据错
				   { 
				   putchar(0x64);
				    //error=error & 0xfffd; 
				   error=0;	
				       goto end_rx_isr;		 
				   }
		   
			   
			   if(((error & 0x2000)==0x2000 ) || ((error & 0x4000)==0x4000))     
				  { if(((error & 0x2000)==0x0040)  && ((error & 0x4000)==0x4000))
				     {                                                             // a b
				      putchar(0x55);
				      error=0;
				      goto end_rx_isr;
				     }
				    else if((error & 0x2000)==0x2000)              // a ?                                 // 断线 a
				     {
				      putchar(0x53);
				      error=0;
				      goto end_rx_isr;
				      }
				    else if((error & 0x4000)==0x4000)             // b 
				     {
				      putchar(0x54);
				      error=0;
				      goto end_rx_isr;
				      }
				    else
				      {;}
				   }
				
			     putchar(headcode);
			     error=0;
			     goto end_rx_isr;
					}
				} 
	    	    
	     
	     if (getchar1==0xcf)                                                // 查询通讯数据对否
	     {
	      if((error & 0x1000)==0x1000) 
	      {error=error&0xefff;
	      putchar(0x64);}
	      else
	      {
	       putchar(headcode);}
	       reshu=0; 
	       addreffect=0;
	       
	      goto end_rx_isr;}	      
	      if (getchar1==0xd0)// 查询通讯状态，绣作中查错
	     { 
	     	if((moveafinish & movebfinish) ==0) // 5.19 电机在转报忙，退出
	      {  
	      	putchar(0x62);  //剪刀忙
	        goto end_rx_isr;//退出接收中断
	      }
	      if(error==0) // 没错误，回板地址  
		    { 
		    	if(jianxian==1)
		    	{		      
		      	if(uartempty<2)//一包数据中，没有收够两个数据
	            {
	             putchar(0x90);//数据丢失
	            }
	          else 
	          	putchar(headcode);//返回板地址，在哪里对headcode赋值？在main函数开始的地方，已经将板地址赋值给它；
	          uartempty=0;
	      	}
	        else if(jitou==1)
	        {
	          
	          if(uartempty<1)
	            {
	             putchar(0x91);//上机头数据丢失
	            }  
	          else 
	          	putchar(headcode);
	          uartempty=0;
	        }
	        else
	        {
	        	putchar(headcode);//其他情况下返回板地址
	        }
			 	goto end_rx_isr;
			 }
		    else {
		       
		        if(((error & 0x0002)==0x0002 ) || ((error & 0x0004)==0x0004))     //断线
				  { if((((error & 0x0002)==0x0002) && (a_lock1==0)) && (((error & 0x0004)==0x0004) && (b_lock1==0)))
				     {                                                             // a b
				      putchar(0x13);
				      error=0;
				      goto end_rx_isr;
				     }
				    else if(((error & 0x0002)==0x0002) && (a_lock1==0))             // a 断线                                  // 断线 a
				     {
				      putchar(0x11);
				      error=0;
				      goto end_rx_isr;
				      }
				    else if(((error & 0x0004)==0x0004) && (b_lock1==0))            // b 断线
				     {
				      putchar(0x12);
				      error=0;
				      goto end_rx_isr;
				      }
				    else
				      {;}
				   }
				   
				if(((error & 0x0100)==0x0100 ) || ((error & 0x0200)==0x0200))     // 针高异常
				  { if((((error & 0x0100)==0x0100) && (a_lock1==0)) && (((error & 0x0200)==0x0200) && (b_lock1==0)))
				     {                                                             // a b
				      putchar(0x06);
				      error=0;
				      goto end_rx_isr;
				     }
				    else if(((error & 0x0100)==0x0100) && (a_lock1==0))             // a ?                                 // 断线 a
				     {
				      putchar(0x04);
				      error=0;
				      goto end_rx_isr;
				      }
				    else if(((error & 0x0200)==0x0200) && (b_lock1==0))            // b 
				     {
				      putchar(0x05);
				      error=0;
				      goto end_rx_isr;
				      }
				    else
				      {;}
				   }
		
				
			    
				if((error & 0x1000)==0x1000)          // CRC数据错
				   { 
				   putchar(0x64);
				    //error=error & 0xfffd; 
				   error=0;	
				       goto end_rx_isr;		 
				   }
		   
				   
			     if(((error & 0x2000)==0x2000 ) || ((error & 0x4000)==0x4000))     
				  { if(((error & 0x2000)==0x0040)  && ((error & 0x4000)==0x4000))
				     {                                                             // a b
				      putchar(0x55);
				      error=0;
				      goto end_rx_isr;
				     }
				    else if((error & 0x2000)==0x2000)              // a ?                                 // 断线 a
				     {
				      putchar(0x53);
				      error=0;
				      goto end_rx_isr;
				      }
				    else if((error & 0x4000)==0x4000)             // b 
				     {
				      putchar(0x54);
				      error=0;
				      goto end_rx_isr;
				      }
				    else
				      {;}
				   }
				   
			   if(jianxian==1)
		    { 
		      if(uartempty<2)
	            {
	             putchar(0x90);
	            }
	          else putchar(headcode);
	          uartempty=0;
	        }
	        else if(jitou==1)
	        { 
	          if(uartempty<1)
	            {
	             putchar(0x91);
	            }
	          else putchar(headcode);
	          uartempty=0;
	        }
	        else
	        {putchar(headcode);}		 	   	  	   	   
				 uartempty=0;
			     //putchar(headcode);
			     error=0;
			     goto end_rx_isr;
					}
	      
	       

		} 
	    	    
	    if (getchar1==0xd1)                                               // 查询通讯状态
	     { if((moveafinish & movebfinish) ==0)                              // 5.19 电机在转报忙，退出
	      {  putchar(0x62);
	         goto end_rx_isr;
	      }
	        
	        putchar(39);
	        goto end_rx_isr;

		}   
		
		if (getchar1==0xd2)                                               
	     { 
	      if(jitou==1)
	       {
	        if((P4IN&0x40)==0x40)
	        { putchar(0x70);
	        }
	        else
	        { putchar(0x71);
	        }
	       }
	      else
	      {;}
	      
	       goto end_rx_isr;
		 }     
	     
	     
	     }
	     }
	     goto end_rx_isr;
	     } 
	    
	     //                             数据描述  	    
	    if (data1==0xc9)//当前机器速度，花样角度, 第一个数  方向+速度      第二个数   角度
	    {
	    	shuju=1;
	      describe=0;
	      goto end_rx_isr;
	     } 
	     if (data1==0xc8)
	      {
	      	describe=0;
	     		goto end_rx_isr;
	     	} 
	     if (data1==0xc7)
	    	{
	    		jiandaoshuju=1;
	     		describe=0;
	     		goto end_rx_isr;
	     	}
	     
	     if (data1==0xc6)
	    {zhengaoshuju=1;
	     describe=0;
	     //other=1;
	     goto end_rx_isr;}
	     
	    if (data1==0xc5)                   // 开关数据
	    { swshuju=1;
	      describe=0;
	     //other=1;
	     goto end_rx_isr;} 
	     
	     if ((data1==0xc4) && (jitou==1))                           // 断检数据
	    { djshuju=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	     if ((data1==0xc3) && (jianxian==1))                        // 环偏移数据           
	    { PYshuju=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	      if ((data1==0xc2))                       // 找原点数据        
	    { yuanshuju=1;
	      describe=0;
	     goto end_rx_isr;}
	     
	     if (data1==0xc1)                        // 找穿线点数据         
	    { chuanshuju=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	     if ((data1==0xc0) && (jianxian==1))                        // 换色数据          
	    { Hsshuju1=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	     if(data1==0xbf)// 关闭机头数据         
	    { jtshuju=1;
	      describe=0;
	     goto end_rx_isr;}
	     
	      if((data1==0xbe) && (jitou==1))// D数据         
	    { Dshuju=1;
	      describe=0;
	     goto end_rx_isr;} 
   
          if((data1==0xbd) && (jitou==1))                           //   
	    { zhentestshuju=1;
	      describe=0;
	     goto end_rx_isr;} 
	     	    
	     
	      if(data1==0xbc)                          //   
	    { uarttestshuju=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	     if (data1==0xbb)                        // test数据          
	    { Hsshuju2=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	     if (data1==0xba)                        //           
	    { bcshuju=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	      if (data1==0xb9)                        //   高16头断检        
	    { djshuju1=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	     if ((data1==0xb8) && (jianxian==1))                        // 换色数据          
	    { HHshuju1=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	      if ((data1==0xb7) && (jianxian==1))                        // 换色数据          
	    { jiandaoshuju1=1;
	      describe=0;
	     goto end_rx_isr;} 
	     
	     if (data1==0xb4)                                            // 板功能选择         
	    { banshuju=1;
	      describe=0;
	     goto end_rx_isr;} 
	     	    
	     }
	   else // 收到数据,即收到的东西既不是命令、也不是查询
	   {
	   if(shuju==1) //当前机器速度，花样角度, 第一个数  方向+速度      第二个数   角度                                    
	   {
	   		if(((moveafinish & movebfinish) ==0)||(HHmove==0))              
				   {
				   	addreffect=0;
				    URCTL0=URXWIE;
				    goto end_rx_isr;
				    }
	   
	     		shu=shu+1;
	    		if(shu==1)//第一个数  方向+速度
	    			{
	    				shu11=getchar1;
	     				ccw=shu11&0x80;
	     				speed=shu11&0x7f;
	     				senddata[2]=getchar1;
	     				goto end_rx_isr;
	    			}
	    		else if(shu==2)//第二个数   角度
	    			{
	    				shu2=getchar1;
	     				angle1=shu2;
	     				senddata[3]=getchar1;
	     				goto end_rx_isr;}
	    		else if(shu==3)//第三个  校验码1
	    			{
	    				crc1=getchar1;
	     				goto end_rx_isr;
	     			}
	     		else//第三个  校验码2
	     			{ 
	     				crc2=getchar1;
	       			reshu=shu;
	       			crc11=crc1<<8;
	       			reshu1=shu11+shu2;
           		crc3=crc11+crc2;
           		table_crc(senddata,4);
           		if(crc3!=crc)
           			{
           				error|=0x1000;
            			URCTL0=URXWIE;
            			addreffect=0;
            			shuju=0;
            			goto end_rx_isr;
           			}
           		else
           			{
	      					uartempty=uartempty+1;
	      					if ((jitou==1) || (jianxian==1)) //毛巾绣模式
	      					{
	      						if(jitou==1)//上机头
	      							{
	      								mode=4;
	       								HH=1;
	       							}
	      						if(jianxian==1)
	      							{
	      								mode=1;
	       								HH=0;
	       							}
	      						maojinspeed=speed;
	      						maojinangle1=angle1;//给pulse函数用
	      						maojinccw=ccw;
	      						pulse();
	      					}
						     shu=0;
						     crcshuju=0;
						     addreffect=0;
						     URCTL0=URXWIE;
						     shuju=0;
	     					goto end_rx_isr;
	           }
	        }//第三个数据，是校验码 结束
	   }
	   
	   
	  if((jiandaoshuju==1) && (jianxian==1))                  // 收到剪刀数据指令
	   {
	   if((moveafinish & movebfinish) ==0)                    // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	   
	    goto end_rx_isr;}
	   
	     shu=shu+1;
	    if(shu==1)
	    {shu11=getchar1;
	     senddata[2]=shu11;
	     //anglejian1=shu11;
	     goto end_rx_isr;
	    }
	    else if(shu==2)
	    {shu2=getchar1;
	     senddata[3]=shu2;
	     //halfanglejian1=shu2;
	     goto end_rx_isr;
	     }
	    
	    else if(shu==3)
	    {crc1=getchar1;
	     goto end_rx_isr;}
	    else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,4);
           if(crc3!=crc)
           {error|=0x1000;
            addreffect=0;
            URCTL0=URXWIE;
            jiandaoshuju=0;
            goto end_rx_isr;
           }
         else
           {
	    
	     shu=0;
	     crcshuju=0;
             anglejian1=shu11;
             halfanglejian1=shu2;
	     addreffect=0;
	     URCTL0=URXWIE;
	     jiandaoshuju=0;	     
	     goto end_rx_isr;
	     }
	     }
	   }
	   
	    if((jiandaoshuju1==1) && (jianxian==1))                  // 收到剪刀数据指令(speed)
	   {
	   if((moveafinish & movebfinish) ==0)                    // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	   
	    goto end_rx_isr;}
	   
	     shu=shu+1;
	    if(shu==1)
	    {shu11=getchar1;
	     senddata[2]=shu11;
	     
	     goto end_rx_isr;
	    }
	    
	    
	    else if(shu==2)
	    {crc1=getchar1;
	     goto end_rx_isr;}
	    else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,3);
           if(crc3!=crc)
           {error|=0x1000;
            addreffect=0;
            URCTL0=URXWIE;
            jiandaoshuju=0;
            goto end_rx_isr;
           }
         else
           {
	    
	     shu=0;
	     crcshuju=0;
             VATH=shu11;
	     addreffect=0;
	     URCTL0=URXWIE;
	     jiandaoshuju1=0;	     
	     goto end_rx_isr;
	     }
	     }
	   }
	   
	   if((PYshuju==1) && (jianxian==1))                       // 收到偏移数据指令
	   {
	   
	    if((moveafinish & movebfinish) ==0)                    // 12.1
	   {addreffect=0;
	   URCTL0=URXWIE;
	   
	    goto end_rx_isr;}
	   
	    shu=shu+1;
	    if(shu==1)
	    {shu11=getchar1;
	     senddata[2]=shu11;
	     PYcw=shu11&0x80;
	     PYspeed=shu11&0x7f;
	     goto end_rx_isr;
	    }
	    else if(shu==2)
	    {shu2=getchar1;
	     senddata[3]=shu2;
	     PYangle1=shu2;
	     goto end_rx_isr;
	     }
	    else if(shu==3)
	    {crc1=getchar1;
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,4);
        if(crc3!=crc)
           {error|=0x1000;
            addreffect=0;
            URCTL0=URXWIE;
            PYshuju=0;
            goto end_rx_isr;
           }
        else
           {
	     if(jianxian==1)
	     { 
	     mode=3;
	     pulse1();
	     if(chuanxianflag==0)
	     {
	     hdposition=0;
	     hdpositionold=0;
	     }
	     else
	     {hdpositionold=200;
	      hdposition=200;}
	     }
	     shu=0;
	     addreffect=0;
	     URCTL0=URXWIE;
	     PYshuju=0;
	     
	     
	     //P1OUT=P1OUT|0x01;
	     goto end_rx_isr;
	     }
	     }
	   }
	   
	   	if((Dshuju==1) && (jitou==1))                                     
	   {
	   if((moveafinish & movebfinish) ==0)              
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	   
	     shu=shu+1;
	    if(shu==1)
	    {shu11=getchar1;
	     ccw=shu11&0x80;
	     speed=shu11&0x7f;
	     senddata[2]=getchar1;
	     goto end_rx_isr;
	     }
	    else if(shu==2)
	    {shu2=getchar1;
	     angle1=shu2;
	     senddata[3]=getchar1;
	     goto end_rx_isr;}
	    else if(shu==3)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,4);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            addreffect=0;
            shuju=0;
            goto end_rx_isr;
           }
          else
         {
	      
	      mode=4;
	      HH=1;
	     
	      maojinspeed=speed;
	      maojinangle1=angle1;
	      maojinccw=ccw;
	     
	      if (HHmove!=0)
	      {pulse();}
	      
	 
	     shu=0;
	     crcshuju=0;
	     addreffect=0;
	     URCTL0=URXWIE;
	     Dshuju=0;
	     
	     goto end_rx_isr;
	     }
	   }
	   }
	   
	   if((Hsshuju1==1) && (jianxian==1))                      // 收到换色数据指令
	   {
	   
	    if((moveafinish & movebfinish) ==0)                    // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	   
	    shu=shu+1;
	    if(shu==1)
	    {shu11=getchar1;
	     senddata[2]=shu11;
	     
	     goto end_rx_isr;
	    }
	    else if(shu==2)
	    {shu2=getchar1;
	     senddata[3]=shu2;
	    
	     goto end_rx_isr;
	     }
	    else if(shu==3)
	    {crc1=getchar1;
	     goto end_rx_isr;
	     }
	     else
	     {crc2=getchar1;
	      reshu=shu;
	      crc11=crc1<<8;
          crc3=crc11+crc2;
          table_crc(senddata,4);
          if(crc3!=crc)
          {error|=0x1000;
           addreffect=0;
           Hsshuju1=0;
           URCTL0=URXWIE;
            goto end_rx_isr;
          }
        else
         {
	     Huansecw=shu11&0x80;
	     
	     HSspeed=shu11&0x7f; 
             Huanseangle1=shu2*135;
	     if(jianxian==1)
	     { 
	     //mode=5;
	     pulse4();
	     }
	     shu=0;
	     addreffect=0;
	     URCTL0=URXWIE;
	     Hsshuju1=0;
	     
	     
	     //P1OUT=P1OUT|0x01;
	     goto end_rx_isr;
	     }
	   }
	   } 
	   
	   if((HHshuju1==1) && (jianxian==1))                      // 收到换色数据指令
	   {
	   
	    if((moveafinish & movebfinish) ==0)                    // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	   
	    shu=shu+1;
	    if(shu==1)
	    {shu11=getchar1;
	     senddata[2]=shu11;
  
	     //HHspeed=shu11&0x7f;
	     goto end_rx_isr;
	    }
	    else if(shu==2)
	    {shu2=getchar1;
	     senddata[3]=shu2;
	     //HHangle1=7+2*shu2;
	     goto end_rx_isr;
	     }
	    else if(shu==3)
	    {crc1=getchar1;
	     goto end_rx_isr;
	     }
	     else
	     {crc2=getchar1;
	      reshu=shu;
	      crc11=crc1<<8;
          crc3=crc11+crc2;
          table_crc(senddata,4);
          if(crc3!=crc)
          {error|=0x1000;
           addreffect=0;
           HHshuju1=0;
           URCTL0=URXWIE;
            goto end_rx_isr;
          }
        else
         {
	     shu=0;
	     addreffect=0;
	     URCTL0=URXWIE;
	     HHshuju1=0;
	      if(shu2>20)
	     {shu2=20;}
	     HHangle1=7+2*shu2;
	     
	     HHspeed=shu11&0x7f;
	     
	     //P1OUT=P1OUT|0x01;
	     goto end_rx_isr;
	     }
	   }
	   } 
	   
	    if(Hsshuju2==1)                                        // 收到test数据指令
	   {
	   
	    if((moveafinish & movebfinish) ==0)                    // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	   
	    shu=shu+1;
	    if(shu==1)
	    {shu11=getchar1;
	     senddata[2]=shu11;
	     
	     goto end_rx_isr;
	    }
	    else if(shu==2)
	    {shu2=getchar1;
	     senddata[3]=shu2;
	     
	     goto end_rx_isr;
	     }
	    else if(shu==3)
	    {crc1=getchar1;
	     goto end_rx_isr;
	     }
	     else
	     {crc2=getchar1;
	      reshu=shu;
	      crc11=crc1<<8;
          crc3=crc11+crc2;
          table_crc(senddata,4);
          if(crc3!=crc)
          {error|=0x1000;
           addreffect=0;
           Hsshuju1=0;
           URCTL0=URXWIE;
            goto end_rx_isr;
          }
        else
         {
	     Huansecw=shu11&0x80;
	     HSspeed=shu11&0x7f;
       Huanseangle1=shu2*135; 
	     mode=8;
	     pulse8();
	     
	     shu=0;
	     addreffect=0;
	     URCTL0=URXWIE;
	     Hsshuju2=0;
	     
	     
	     //P1OUT=P1OUT|0x01;
	     goto end_rx_isr;
	     }
	   }
	   } 
	   
	   if(jtshuju==1)                                     // 收到机头数据指令
	   {
	    
	    if((moveafinish & movebfinish) ==0)               // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	   
	    goto end_rx_isr;}
	   
	    shu=shu+1;
	    
	    if(shu==1)
	    {shu1=getchar1;
	     senddata[2]=shu1;
	     shu11=shu1<<16;
	     shu11=shu11<<8;
	     goto end_rx_isr;
	    }
	    else if(shu==2)
	    {shu2=getchar1;
	     senddata[3]=shu2;
	     shu21=shu2<<16;
	     goto end_rx_isr;
	     }
	    else if(shu==3)
	    {shu3=getchar1;
	     senddata[4]=shu3;
	     shu31=shu3<<8;
	     goto end_rx_isr;
	     }
	    else if(shu==4)
	     {shu4=getchar1;
	      senddata[5]=shu4;
	      goto end_rx_isr;
	      }
	    else if(shu==5)
	      {crc1=getchar1;
	       goto end_rx_isr;
	      }
	    else
	      {crc2=getchar1;
	      reshu=shu;
	      crc11=crc1<<8;
          crc3=crc11+crc2;
          table_crc(senddata,6);
          if(crc3!=crc)
          {error|=0x1000;
           addreffect=0;
           jtshuju=0;
           URCTL0=URXWIE;
           goto end_rx_isr;
          }
        else
         {
          fheadcode=headcode&0x0f;
          if((headcode==0xde)||(headcode==0xdf))
          {fheadcode=16;}
	      shuju32=shu11+shu21+shu31+shu4;
	      yiwei=2*(fheadcode-1);
	      jtshu=shuju32>>yiwei;
	      if((jtshu&0x01)==0)
	      {a_lock1=0;}
	      else
	      {a_lock1=1;}
	      if((jtshu&0x02)==0)
	      {b_lock1=0;}
	      else
	      {b_lock1=1;}
	     
	     
	     shu=0;
	     addreffect=0;
	     URCTL0=URXWIE;
	     jtshuju=0;
	     
	     
	     //P1OUT=P1OUT|0x01;
	     goto end_rx_isr;
	     }
	   }
	  }
	  
	  
	    if(yuanshuju==1)                                       // 收到找原点数据
	   {
	   if((moveafinish & movebfinish) ==0)                     // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	    shu=shu+1;
	    if(shu==1)
	    {
	     senddata[2]=getchar1;
	     goto end_rx_isr;
	    }
	    
	    else if(shu==2)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,3);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            yuanshuju=0;
            addreffect=0;
            goto end_rx_isr;
           }
         else
         {
	    
	     zhenwei=senddata[2]&0x0f;
	     
	      if((senddata[2]&0x30)==0)
	     {putdata1=0x7ff;}
	     else if((senddata[2]&0x30)==0x10)
	     {putdata1=0x7fd;}
	     else if((senddata[2]&0x30)==0x20)
	     {putdata1=0x7fc;}
	     else if((senddata[2]&0x30)==0x30)
	     {putdata1=0x7ff;}
	     //zhenwei=1;
	     mode=2;
	     
	     pulse2();
	     
	     addreffect=0;
	     URCTL0=URXWIE;
	     shu=0;
	     yuanshuju=0;

	     //P1OUT=P1OUT|0x01;
	     goto end_rx_isr;
	    }
	  }
	 }
	    
	    if((chuanshuju==1))                   // 收到找穿线点数据
	   {
	   if((moveafinish & movebfinish) ==0)                     // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	    shu=shu+1;
	    if(shu==1)
	    {
	     senddata[2]=getchar1;
	     goto end_rx_isr;
	    }
	    
	    else if(shu==2)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,3);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            chuanshuju=0;
            addreffect=0;
            goto end_rx_isr;
           }
         else
         {
	     //if(jianxian==1)
	     //{
	     zhenwei=senddata[2]&0x0f;
	     mode=2;
	     putdata1=0x7ff;
	     pulse3();
	     //}
	     //if(jitou==1)
	     //{
	     addreffect=0;
	     URCTL0=URXWIE;
	     shu=0;
	     chuanshuju=0;

	     //P1OUT=P1OUT|0x01;
	     goto end_rx_isr;
	    }
	  }
	 }
	   

	   if((zhengaoshuju==1) && (jitou==1))                     // 收到针高数据指令
	   {
	   if((moveafinish & movebfinish) ==0)                     // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	    shu=shu+1;
	    if(shu==1)
	    {
	     senddata[2]=getchar1;
	     goto end_rx_isr;
	    }
	    
	    else if(shu==2)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,3);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            addreffect=0;
            zhengaoshuju=0;
            goto end_rx_isr;
           }
         else
         { jitoutest=0;
	      jiwei=senddata[2];
	      if(jiwei>10)
	      {jiwei=10;}
	      if(((jitou==1) && (atzero==1)) && (startdo==0))
	        {
	        error=0;
            if(buxiu_flage)
			  {
			   if(a_buxiu) 
			   		posivaluea=posivalue[jiwei];
			   else 
			   		posivaluea=posivalue[10];
			   if(b_buxiu) 
			   		posivalueb=posivalue[jiwei];
			   else 
			   		posivalueb=posivalue[10];
			   move1(0); 
			   move1(1);                                                        //oooooooooooooooooo
			  }
	         else		 
		     {if(a_lock) posivaluea=posivalue[10];
		      else posivaluea=posivalue[jiwei];  
	   			     
		      if(b_lock) posivalueb=posivalue[10];
		      else posivalueb=posivalue[jiwei];
		          move1(0);
			      move1(1);
	          } 
	      }   
	     addreffect=0;
	     URCTL0=URXWIE;
	     
	     zhengaoshuju=0;

	     //P1OUT=P1OUT|0x01;
	     goto end_rx_isr;
	    }
	    }
	   }
	   
	   if((zhentestshuju==1) && (jitou==1))                                     
	   {
	   if((moveafinish & movebfinish) ==0)              
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	   
	     shu=shu+1;
	    if(shu==1)
	    {shu11=getchar1;
	     cwneedlehigh=shu11&0x80;
	     zhenspeed1=shu11&0x7f;
	     senddata[2]=getchar1;
	     goto end_rx_isr;
	     }
	    else if(shu==2)
	    {shu2=getchar1;
	     needleangle=shu2;
	     senddata[3]=getchar1;
	     goto end_rx_isr;}
	    else if(shu==3)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       
	       	 crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,4);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            addreffect=0;
            shuju=0;
            goto end_rx_isr;
           }
          else
         {
	      
	      jitoutest=1;
	     
	     
	      if (moveafinish & movebfinish)
	      {move1(0);}
	      
	 
	     shu=0;
	     crcshuju=0;
	     addreffect=0;
	     URCTL0=URXWIE;
	     zhentestshuju=0;
	     
	     goto end_rx_isr;
	     }
	   }
	   }
	   
	   if((swshuju==1) && (jianxian==1))                                         // 收到开关数据
	   {shu=shu+1;
	    if(shu==1)
	    {
	     senddata[2]=getchar1;
	     goto end_rx_isr;
	    }
	    
	    else if(shu==2)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,3);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            addreffect=0;
            swshuju=0;
            goto end_rx_isr;
           }
         else
         {
         addreffect=0;
	     URCTL0=URXWIE;
	    if(jianxian==1)
	    {
	    pa1=senddata[2];
	    b_lock=pa1&0x01;
	    b_buxiu=(pa1&0x02)>>1;
	    //if(pa1&0x02==0x02) b_buxiu=1;
	    //else b_buxiu=0;
	    a_lock=(pa1&0x04)>>2;
	    //if(pa1&0x08==0x08) a_buxiu=1;
	    //else a_buxiu=0;
	    a_buxiu=(pa1&0x08)>>3;
	    }
	    goto end_rx_isr;
	   }
	  }
	 }
	   
	    if(uarttestshuju==1)                                     
	   {
	   if((moveafinish & movebfinish) ==0)              
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	   
	     shu=shu+1;
	    if(shu==1)
	    {shu11=getchar1;
	     
	     senddata[2]=getchar1;
	     goto end_rx_isr;
	    }
	    else if(shu==2)
	    {shu2=getchar1;
	     
	     senddata[3]=getchar1;
	     goto end_rx_isr;}
	    else if(shu==3)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       
	       reshu1=shu11+shu2;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,4);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            addreffect=0;
            shuju=0;
            goto end_rx_isr;
           }
           else
           {
	      
	      putchar(reshu1);
	    
	     shu=0;
	     crcshuju=0;
	     addreffect=0;
	     URCTL0=URXWIE;
	     shuju=0;
	     
	     goto end_rx_isr;
	     }
	   }
	   } 
	   
	   if((djshuju==1) && (jitou==1))                                    // 收到断检数据
	   {shu=shu+1;
	    if(shu==1)
	    {
	     senddata[2]=getchar1;
	     djzt1=getchar1<<8;
	     goto end_rx_isr;
	    }
	    if(shu==2)
	    {
	     senddata[3]=getchar1;
	     djzt2=getchar1;
	     goto end_rx_isr;
	    }
	    else if(shu==3)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,4);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            addreffect=0;
            djshuju=0;
            goto end_rx_isr;
           }
         else
         {
	     addreffect=0;
	     URCTL0=URXWIE;
	     djzt=djzt1+djzt2;
	    if(jitou==1)
	    {fheadcode=headcode&0x0f;
	     if(fheadcode<=8)
	     {
	     yiwei=2*(fheadcode-1);
	     djzt=djzt>>yiwei;
	     djzt3=djzt&0x03;
	    if(djzt3==0x03)
	      { gal();
	        gbl();
	        lar();
	        lbr();
	        a_buxiu=1;
	        b_buxiu=1;
	        goto end_rx_isr;
	        }         
	    else if(djzt3==0x01)
	       {
	        gal();
	        lar();
	        a_buxiu=1;
	        goto end_rx_isr;
	        }
	        
	    else if(djzt3==0x02)
	      { gbl();
	        lbr();
	        b_buxiu=1;
	        goto end_rx_isr;
	        } 
	     }
	     else
	     {   
	      goto end_rx_isr;
	     }
	    }
	    goto end_rx_isr;
	   } 
      }
     }
     
      if((djshuju1==1) && (jitou==1))                                    // 收到断检数据
	   {shu=shu+1;
	    if(shu==1)
	    {
	     senddata[2]=getchar1;
	     djzt1=getchar1<<8;
	     goto end_rx_isr;
	    }
	    if(shu==2)
	    {
	     senddata[3]=getchar1;
	     djzt2=getchar1;
	     goto end_rx_isr;
	    }
	    else if(shu==3)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,4);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            addreffect=0;
            djshuju1=0;
            goto end_rx_isr;
           }
         else
         {
	     addreffect=0;
	     URCTL0=URXWIE;
	     djzt=djzt1+djzt2;
	    if(jitou==1)
	    {fheadcode=headcode&0x0f;
	     if((headcode==0xdf)||(headcode==0xde))
	     {fheadcode=16;}
	     if(fheadcode>8)
	     {
	     yiwei=2*(fheadcode-1)-16;
	     djzt=djzt>>yiwei;
	     djzt3=djzt&0x03;
	    if(djzt3==0x03)
	      { gal();
	        gbl();
	        lar();
	        lbr();
	        a_buxiu=1;
	        b_buxiu=1;
	        goto end_rx_isr;
	        }         
	    else if(djzt3==0x01)
	       {
	        gal();
	        lar();
	        a_buxiu=1;
	        goto end_rx_isr;
	        }
	        
	    else if(djzt3==0x02)
	      { gbl();
	        lbr();
	        b_buxiu=1;
	        goto end_rx_isr;
	        } 
	       }
	       else
	       { 
	        goto end_rx_isr;
	       }
	    }
	    goto end_rx_isr;
	   } 
      }
     }
     
	  if(bcshuju==1)                      // 收到针高数据指令
	   {
	   if((moveafinish & movebfinish) ==0)                     // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	    shu=shu+1;
	    if(shu==1)
	    {
	     senddata[2]=getchar1;
	     goto end_rx_isr;
	    }
	    
	    else if(shu==2)
	    {crc1=getchar1;
	     
	     goto end_rx_isr;}
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
           crc3=crc11+crc2;
           table_crc(senddata,3);
           if(crc3!=crc)
           {error|=0x1000;
            URCTL0=URXWIE;
            addreffect=0;
            bcshuju=0;
            goto end_rx_isr;
           }
         else
         { 
	      buc=senddata[2];
               if(buc>8)                             // 07.05,21
                {buc=8;}                              //07.05.21
	     goto end_rx_isr;
	    }
	    }
	   }  
	   
	   if(banshuju==1)                      // 板功能选择
	   {
	   if((moveafinish & movebfinish) ==0)  // 12.1
	   {addreffect=0;
	    URCTL0=URXWIE;
	    goto end_rx_isr;}
	    shu=shu+1;
	    if(shu==1)
	    {
	     senddata[2]=getchar1;
	     goto end_rx_isr;
	    }
	    
	    else if(shu==2)
	    {
	    	crc1=getchar1;
	     	goto end_rx_isr;
	    }
	     else
	     { crc2=getchar1;
	       reshu=shu;
	       crc11=crc1<<8;
         crc3=crc11+crc2;
         table_crc(senddata,3);
           if(crc3!=crc)
           {
           	error|=0x1000;
            URCTL0=URXWIE;
            addreffect=0;
             banshuju=0;
            goto end_rx_isr;
           }
         else//CRC校验正确
         { 
	         if(senddata[2]==0)
	         {
	         	boardnum=0;
	         }
	         else if(senddata[2]==1)
	         {
	         	boardnum=1;
	         }
	         else
	         {
	         	boardnum=0;
	         }
		     goto end_rx_isr;
	    	}//结束CRC校验正确
	    }//结束获取第三个数据
	   }//结束if(banshuju==1)  // 板功能选择
	  addreffect=0;
	  URCTL0=URXWIE;

	          
        //  putchar(0x13);
	    // getchar1=0x13;         //give it a unuseful value
//uart has received a character in UDR                           */
     }
     }//结束地址有效，所以在地址无效的情况下，这个函数是很短的
end_rx_isr: ;
  
 }

 void avaluetest(void)
  { 
   if((adcvaluea>>2)>maxa)
   { 
   	maxa=adcvaluea>>2;}
    else if((adcvaluea>>2)<mina) 
    { 
    	mina=adcvaluea>>2;
    }
    else
     {;}
   }

void bvaluetest(void)
 { 
 if((adcvalueb>>2)>maxb)
 { maxb=adcvalueb>>2;}
 else if((adcvalueb>>2)<minb) 
 { minb=adcvalueb>>2;}
 else
 {;}
}

//  针位置检测函数
void apositest(void)
{ 
 u8 positesta;  
  for(positesta=0;positesta<11;positesta++) 
	       { if(positesta==10)
		       {if((adcvaluea<posivalue[positesta]+18) && (adcvaluea>posivalue[positesta]-18))
			    break;
			   }
		     if(positesta==0)
		       {if((adcvaluea<=posivalue[positesta]+16) && (adcvaluea>posivalue[positesta]-24))
			    break;
			   }
		      if(adcvaluea<=posivalue[positesta]+16 && (adcvaluea>posivalue[positesta]-16))
                { break;}
		   }
	   positiona=positesta;	
	   if(positiona==positionaold)
	   {position+=1;}
	   if(positiona!=positionaold)
	   {position=0;}
	   if(position>5)
	   {positiona1=positiona;
	   position=0;}
	   positionaold=positiona;
	   
  

} 


void bpositest(void)
{ u8 positestb;

 for(positestb=0;positestb<11;positestb++) 
	       { if(positestb==10)
		     {if((adcvalueb<posivalue[positestb]+18) && (adcvalueb>posivalue[positestb]-18))
		      break;
			  }
			 
		     if(positestb==0)
		     {if((adcvalueb<=posivalue[positestb]+16) && (adcvalueb>posivalue[positestb]-24))
		      break;
			  }
			  
		      if(adcvalueb<=posivalue[positestb]+16 && (adcvalueb>posivalue[positestb]-16))
                { break;
		        }
		   }
	   positionb=positestb;
	   if(positionb==positionbold)
	   {position1+=1;}
	   if(positionb!=positionbold)
	   {position1=0;}
	   if(position1>5)
	   {positionb1=positionb;
	    position1=0;}
	   positionbold=positionb;
	  
}

 //  针高 剪刀电机电流控制函数
 void current_control(void)                          //电流控制子程
 {//每路电机有两路采样，所以有4个AD判断
   static u8 k1=0,k2=0,k3=0,k4=0;
   
   ADDATA1 = ADC12MEM[0];                            // Move results, IFG is cleared                       
   ADDATAH=ADDATA1>>4;                               // SAVE HIGH 8 BIT RESULT 
   
   if (ADDATA1>3940 || ADDATA1<100)                   // current protect
   { 
      k1+=1;
      if (k1>=8)
      {
        //P2OUT=P2OUT&0xFD;
        P1OUT=P1OUT&0xfb;//超过8次，关闭使能信号
        lar();//亮红灯
      }
   }
   else
   { 
     k1=0;
   }//结束剪线和针高电流AD采样的情况
   if(h2==0X00)//大电流情况
  { 
     CURRENTVALUE1=CURRENTVALUEa1[pointer2];
       //ADDATAH=ADDATA1H;
       P=4;
       pwmc();//这里面主要是变化PWMS1
       TBCCR1=PWMS1;
   }
    else//小电流情况
      {//CURRENTVALUE1=CURRENT0A[pointer2];            // HALF CURRENT MODE
      
       //ADDATAH=ADDATA1H;
       //P=1;
       //pwmc();
      if(jitou==1)//针高
      {
        KV2=PWM1A1[pointer2]-100;
        KV2=KV2*ZXS/8;
        TBCCR1=100+KV2;
      }
      else if(jianxian==1)//剪线
      {
        TBCCR1=PWM1A2[pointer2];
      } 
       //TBCCR1=100;
    }   
  
       
       
                                                    // motor1 coin A
   
  
    ADDATA2 = ADC12MEM[1];                         // Move results, IFG is cleared
    ADDATAH=ADDATA2>>4;                            // SAVE HIGH 8 BIT RESULT
    
    if (ADDATA2>3940 || ADDATA2<100)                   // current protect
   { k2+=1;
    if (k2>=8)
    {
    //P2OUT=P2OUT&0xFd;
    P1OUT=P1OUT&0xfb;
    lar();}
   }
   else
   { k2=0;}
    
   //if (ADDATAH>250 || ADDATAH<5)                 // current protect
   //{
   //P2OUT=P2OUT&0xF9;
   //}
   
   //h1=PORTA&0x04;
   if(h2==0X00)
  { 
                                                      
   
    CURRENTVALUE1=CURRENTVALUEb1[pointer2];
   
   
       
       //ADDATAH=ADDATA2H;
       P=4;
       pwmc();
       TBCCR2=PWMS1;
   }
  
    else
      {//CURRENTVALUE1=CURRENT0B[pointer2];            // HALF CURRENT MODE
      
       //ADDATAH=ADDATA2H;
      // P=1;
       //pwmc();
       if(jitou==1)
      {KV2=PWM1B1[pointer2]-100;
       KV2=KV2*ZXS/8;
       TBCCR2=100+KV2; }
      else if(jianxian==1)
      {TBCCR2=PWM1B2[pointer2];} 
       //TBCCR2=100;
    }   
  
       
                                                    // motor1 coin B
   
  
   
   ADDATA3 = ADC12MEM[2];                            // Move results, IFG is cleared                       
   ADDATAH=ADDATA3>>4;                               // SAVE HIGH 8 BIT RESULT 
   
   if (ADDATA3>3840 || ADDATA3<200)                   // current protect
   { k3+=1;
    if (k3>=4)
    {
     //P2OUT=P2OUT&0xFb;
     P1OUT=P1OUT&0xfb;
     lbr();}
   }
   else
   { k3=0;}
   
   //if (ADDATAH>250 || ADDATAH<5)                    // current protect
   //{P2OUT=P2OUT&0xF9;}
   
   //h2=PORTA&0x02;
   if(h1==0X00)
  { 
    
   CURRENTVALUE1=CURRENTVALUEa1[pointer1];
       //ADDATAH=ADDATA3H;
       P=4;
       pwmc();
       TBCCR3=PWMS1;
   }
  
    else
      {//CURRENTVALUE1=CURRENT0A[pointer1];            // HALF CURRENT MODE
      
       //ADDATAH=ADDATA3H;
       //P=1;
      // pwmc();
      if(jitou==1)
      {
     KV2=PWM1A1[pointer1]-100;
       KV2=KV2*ZXS/8;
       TBCCR3=100+KV2; }
      else if(jianxian==1)
      {TBCCR3=PWM1A2[pointer1];} 
      //TBCCR3=100;
    }   
  
       
                                                     // motor2 coin A
  
    
   ADDATA4 = ADC12MEM[3];                            // Move results, IFG is cleared                       
   ADDATAH=ADDATA4>>4;                               // SAVE HIGH 8 BIT RESULT 
   
   if (ADDATA4>3940 || ADDATA4<100)                   // current protect
   { k4+=1;
    if (k4>=4)
    {
    //P2OUT=P2OUT&0xFb;
    P1OUT=P1OUT&0xfb;
     lbr();}
   }
   else
   { k4=0;}
   
   //if (ADDATAH>250 || ADDATAH<5)                     // current protect
   //{P2OUT=P2OUT&0xF9;}
   
   //h2=PORTA&0x02;
   if(h1==0X00)
  { 
                                                      
   
   
   CURRENTVALUE1=CURRENTVALUEb1[pointer1];
       //ADDATAH=ADDATA4H;
       P=4;
       pwmc();
       TBCCR4=PWMS1;
   }
  
    else
      {//CURRENTVALUE1=CURRENT0B[pointer1];            // HALF CURRENT MODE
      
       //ADDATAH=ADDATA4H;
      // P=1;
       //pwmc();
       if(jitou==1)
      {
      KV2=PWM1B1[pointer1]-100;
       KV2=KV2*ZXS/8;
       TBCCR4=100+KV2; }
      else if(jianxian==1)
      {TBCCR4=PWM1B2[pointer1];} 
       //TBCCR4=100;
    }   
     
                                                    // motor2 coin B
                                   
   // P1OUT ^= 0x01;
         
 }
 
 
 
  
void init_devices(void)                             // 初始化子程
{ 
   
  clockinit();
  port_init();   
  TIMEA_3();
  TIMEB_7();   
  ADCINIT();       
  usartinit();
  //usart1init(); 
  mode_select();
  var_init(); 
  
 //all peripherals are now initialised
}
   
 
void main(void)
{                                   
  WDTCTL = WDTPW + WDTHOLD;    					// SET UP WDT 
  P2OUT=P2OUT&0xF9;                     // Stop watchdog timer
  delay(100);
 init_devices();
 delay(100);
 _DINT();                              // DISABLE INTERRUPT
 st:  headcode1=P5IN>>3;                // KNOW WHICH HEAD IT IS!获取P5IN的3、4、5、6、7分别对应DIP4~8
      headcode=headcode1|0xe0;//获取板地址于是headcode就是 1 1 1 * * * * *
      if(headcode==0xe0)      // 07.2.8 DIP3、4、5、6、7是低电平
      {
      	headcode=0xde;  //DIP开关全是ON的时候，第16号板，而且是下机头
      }
      if(headcode==0xf0)//DIP4、5、6、7是低电平 DIP8是高电平，第16号板，而且是上机头
      {
      	headcode=0xdf; //上机头16号板地址
      }                                                                                                
     delay(1);
     tem=P5IN>>3;
     if(headcode1!=tem)
      goto  st; 
   while (1)
   {
   
   // INTIALIZE VARIABLE
   
     //P2OUT=P2OUT&0xF9;                  //  CURRENT PROTECT ON
     P1OUT=P1OUT&0xfb;//P1.2 低电平，针高或者剪线电机不使能
     n=0;
     pointer1=0;
     pointer2=0;
     pointer3=0;
     pointer4=0;
     STOP=0X00;                         // START SIGNAL
     
     if (STOP==0X00)                    // START这里一直为0
     {
     //P2OUT=P2OUT&0xF9;                  //  CURRENT PROTECT ON
     P1OUT=P1OUT&0xfb;//P1.2 低电平，针高或者剪线电机不使能
     E=0;                               
     ADDATA1=0x00;
     ADDATA2=0x00;
     ADDATA3=0x00;
     ADDATA4=0x00;
     ADDATA5=0x00;
     ADDATA6=0x00;
     ADDATAH=0x00;                     // AD RESULT, ERROR
     moveafinish=1; 
     movebfinish=1;//电机转动处于结束状态
    
    current_select();                  // select current
    step_select();                     // step select
    
     PWMS1=100;//设定pwm的周期，即占空比
    
     TACTL |= MC1;                    // Start Timer_A in continuous mode
     TBCTL |= MC1+MC0;                // Start Timer_B in up_down mode
    ADC12CTL0 |= ADC12SC;            // Start conversion
    adcvaluea=ADC12MEM[4]>>2;
    adcvalueb=ADC12MEM[5]>>2; 
     delay(1000);
     delay(1000);
     delay(1000);
     
     P1OUT^=0x01;//给DSP的XINT几个波形
     delay(100);
     P1OUT^=0x01;
     delay(100);
     P1OUT^=0x01;
     delay(100);
     P1OUT^=0x01;
     delay(100);
     P1OUT^=0x01;
     delay(100);
     P1OUT^=0x01;
     
      _EINT();                        // all maskable interrupt on 
     //P2OUT |=0x06;;                    // enable on 
     P1OUT|=0x04;//针高或者剪线电机使能
     h1=1;
     h2=1;
     ADC12CTL0 |= ADC12SC;            // Start conversion
     while(1)                                                           // start
      { //P4OUT^=0x40;
         current_control();
         adcvaluea=ADC12MEM[4]>>2;
         adcvalueb=ADC12MEM[5]>>2;
         //current_control(); 
          //putchar(0x10);
         //b_lock1=1;
       if(moveafinish & movebfinish)// motor a,b stop 剪线、针高轴在停止过程中查错误
          {
          //current_control();
          if(HHmove==1)//HHmove在什么情况下是1？初始化为1，角度走完后设置为1
          {
           HHmove1=HHmove1+1;
           if(HHmove1<20)
           {delay(15);}
           else if(HHmove1<40)
           {//P1OUT|=0x80;
            s7=P2IN&0x01;//DSP的A路电机异常信号
	    s8=P5IN&0x01;//DSP的B路电机异常信号
            if(s7==0)//A路电机低电平异常
             {
              s7tem2=s7tem2+1;
              if(s7tem2>60)
              {
                s7tem2=0;
                s7tem1=0;
                error|=0x2000;
              }
             }//结束if(s7==0)
             else //检查到正常
             {
               s7tem1=s7tem1+1;
               if(s7tem1>2)
                  s7tem1=0;
               s7tem2=0;//清上次的异常
               error&=0xdfff;//清上次的异常处理标志
             }
             if(s8==0)//DSP的B电机异常
             {
               s8tem2=s8tem2+1;
              if(s8tem2>60)
               {
                 s8tem2=0;
                s8tem1=0;
                error|=0x4000;
               }
              }//结束if(s8==0)
              else
             {
                s8tem1=s8tem1+1;
                if(s8tem1>2)
                    s8tem1=0;
                s8tem2=0;
               error&=0xbfff;
             }
            }//结束else if(HHmove1<40)
           else
           { //P1OUT&=0x7f;
             if(HHmove1>2000)
             {HHmove1=0;}
           }
          }//结束 if(HHmove==1)
          else
          {HHmove1=0;}
            
         /*
          if((HHmove==1))// H or D 在转
	       { 
	        //delay(60);
	        P1OUT|=0x80;
	        //delay(100);
	        s7=P2IN&0x01;
	        s8=P5IN&0x01;
	        
            if(s7==0)
             {s7tem=s7tem+1;
              if(s7tem>6)
              {s7tem=0;
               s7tem1=0;
              error|=0x2000;}}
             else
             {s7tem1=s7tem1+1;
              
              //if(s7tem1>2)
              s7tem1=0;
               s7tem=0;
               error&=0xdfff;}
              
             //s8=P5IN&0x01;
             if(s8==0)
             {s8tem=s8tem+1;
              if(s8tem>6)
               {s8tem=0;
               s8tem1=0;
                error|=0x4000;
               }
              }
              else
             {s8tem1=s8tem1+1;
              
              //if(s8tem1>2)
              s8tem1=0;
               s8tem=0;
               
               error&=0xbfff;}
            }
            else
            {P1OUT&=0x7f;}
          */
          if(jianxian==1)//只有在下机头的时候，变量才是1
          { 
            current_control();
            if((duanjian==1) && (startdo==1) && (duanjian1==1))
            {
              zero_pulse();
            }
          }
          else if (jitou==1)//上机头
          {
           avaluetest();
           bvaluetest();
           apositest();  
           bpositest(); 
	      if(positiona==11)
	        {error21=0; 
	         error11=error11+1;
	         if(error11>10)
	         {
	         if(moveafinish) error5();
	         } 
	            
	        }
	       else
	        {error11=0;
	         error21=error21+1;
	         if(error21>2)
	         {error&=0xfeff;}
	         } 			
	      if(positionb==11)
	        {error22=0;
	         error12=error12+1;
	         if(error12>5)
	         {
	         if(movebfinish) error6();
	         }    
	        }
	       else
	        {error12=0;
	         error22=error22+1;
	         if(error22>2)
	         {error&=0xfdff;}
	        }    
          current_control();
          
          //if(positiona==10)
          //if(positionb==0)
          if(startdo==0)
		  {
		  if((atzero==1)&&(tiaoshiflag==0)) 
                    test_switch();
                  } 
		  
          JP_buxiuA();
          JP_buxiuB();			   
          }	   
	      
          if(shandeng==1 && jitou==1) //上机头和闪灯
            start(3); 
         }
       }//结束while(1)
       }//结束if (STOP==0X00) 
      }//结束第一个while (1)
     }



