import java.io.*;
import java.util.*;



public class Solution1
{

	public String withoutString(String base, String remove)
	{
		int blen = base.length();
		int rlen = remove.length();
		int current = 0;
		int place;
		StringBuilder stbuild = new StringBuilder(blen);
		String blow = base.toLowerCase();
		String rlow = remove.toLowerCase();
		place = blow.indexOf(rlow);
		while(place !=-1)
		{
			for(; current < place; current++)
			{
				stbuild.append(base.charAt(current));
			}
			current = place+rlen;
			place = blow.indexOf(rlow, current);
		}
		for(; current < blen; current++)
		{
			stbuild.append(base.charAt(current));
		}
		return stbuild.toString();
	}
	public static void main(String[] args)
	{
		Solution1 s1=new Solution1();
		System.out.println(s1.withoutString("hello","llo"));
		System.out.println(s1.withoutString("hello","ll"));
	}
}
