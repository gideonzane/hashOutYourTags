'''
Hash Out Your Tags

Features:

	- Generate a list of hashtags for Facebook, Instagram, or Twitter
		- List should include trending hashtags
		- List should be randomized
		- List should include relevant hashtags based on day of week, time of year, etc
		- List should account for recently used tags
		- List should account for tags that gained high amounts of traction
	- Include custom hastags in your posts
		- Set a cap, maybe 10 custom hashtags per profile?
	- With one tap, hashtags are copied to your clipboard
		- Maybe redirect to relevant app's new post page
			- This would probably require permissions
	- Set up multiple profiles for multiple social media accounts
		- ie: one profile for your band's social media, one for your private business, etc
		- Link directly to those accounts
	
	
Notes For Self:
	
	This site has information regarding statistics for optimal number/length of
	hashtags based on platform. This information should be thrown into the mix
	https://www.socialmediatoday.com/social-networks/new-report-looks-optimal-hashtag-use-twitter-instagram-and-facebook
	
'''

from random import randint as rnd

class HashtagList:
	'''
	### CURRENT BUILD ###
	
	- manually add tags to a pool of potential tags
	- manually commit tags for output
	- count number of items in final list
	- count number of characters in final output
	'''
	
	def __init__(self):
		self.list_final = []	# the return list
		self.list_pool = []		# will be filled via webscrape
		self.max_len = 30		# max number to return
		self.max_chars = self.max_len * 40	# <- max len to return
		
		self._MAX_LEN = 30		# hard cap
		self._MAX_CHARS = 700	# hard cap
		
	def __repr__(self):
		ret_str = ''
		for i in self.list_final:
			ret_str += f'#{i} '
		return ret_str			# the return to be copied in to clipboard

	'''
	soft add
	'''
	def add_ht(self, ht):
		self.list_pool.append(ht)
		
	'''
	hard add
	'''
	def commit_ht(self, ht):
	# NOTE: add *args for multiple commits together
		try:
			if ht in self.list_pool:
				if ht not in self.list_final:		# prevent dupes
					self.list_final.append(ht)
			else:
				return 'Error: add hashtag to pool before committing.'
		except:
			pass

	'''
	counts the number of tags stored in list_final
	'''
	def final_len(self):
		return len(self.list_final)
	
	'''
	counts the number of characters in the list_final
	'''
	def final_char_count(self, full = False):
		
		# full char_count includes '#' and ' '
		f_list = self.list_final
		if full:
			f_list = self.__repr__()
			
		all_chars = ''
		for i in f_list:
			all_chars += i
			
		return len(all_chars[:-1])	# slice removes the final ' '
		
		
'''
The below subclasses set parameters based on which platform the user wants to 
generate hastags for. Each includes a setup() method which must be run in order
to set parameters for optimization. Via settings, these parameters can be 
changed per profile.

All instances of the HashtagList should be via one of these subclasses.
'''
		
class ForInsta(HashtagList):
	
	'''
	This method must be run upon creating an instance of this subclass
	'''
	def setup(self):
		self.max_len = 11
		self.max_chars = self.max_len * 24
	
class ForFacebook(HashtagList):
	def setup(self):
		pass
	
class ForTwitter(HashtagList):
	def setup(self):
		pass
