# SmartMybatis3
Write less code to generate a lot of code,Make Mybatis3 become more Smarter and more intelligent.

only one line code ,and you can get the mybatis3 *mapper.xml

this is a test code:

SmartMybatis3Utils.autoCreateMyBatis3MapperFile(CustomerBean.class,CustomerIDao.class,"t_customer","customerId");

++++++++++++++++++++++++auto create CustomerMapper.xml file++++++++++++++++++++++++++++++++++++++++++++++++++++++++

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN" "http://mybatis.org/dtd/mybatis-3-mapper.dtd">

<mapper namespace="test.IDao.CustomerIDao">
  <resultMap type="test.model.CustomerBean" id="customerBeanResultListMap">
    <id property="customerId" column="customerId"/>
    <result property="customerAccount" column="customerAccount"/>
    <result property="customerPassword" column="customerPassword"/>
    <result property="customerNikeName" column="customerNikeName"/>
    <result property="customerToken" column="customerToken"/>
    <result property="customerPhoto" column="customerPhoto"/>
    <result property="customerSex" column="customerSex"/>
    <result property="customerScore" column="customerScore"/>
    <result property="customerLevelId" column="customerLevelId"/>
    <result property="customerRealName" column="customerRealName"/>
    <result property="customerAge" column="customerAge"/>
    <result property="customerRegisterTime" column="customerRegisterTime"/>
  </resultMap>
  <delete id="deleteCustomerById" parameterType="Long">DELETE FROM t_customer WHERE customerId=#{customerId}</delete>
  <update id="updateCustomer" parameterType="test.model.CustomerBean">UPDATE t_customer 
    <set>
      <if test="customerAccount!=null">customerAccount=#{customerAccount},</if>
      <if test="customerPassword!=null">customerPassword=#{customerPassword},</if>
      <if test="customerNikeName!=null">customerNikeName=#{customerNikeName},</if>
      <if test="customerToken!=null">customerToken=#{customerToken},</if>
      <if test="customerPhoto!=null">customerPhoto=#{customerPhoto},</if>
      <if test="customerSex!=null">customerSex=#{customerSex},</if>
      <if test="customerScore!=null">customerScore=#{customerScore},</if>
      <if test="customerLevelId!=null">customerLevelId=#{customerLevelId},</if>
      <if test="customerRealName!=null">customerRealName=#{customerRealName},</if>
      <if test="customerAge!=null">customerAge=#{customerAge},</if>
      <if test="customerRegisterTime!=null">customerRegisterTime=#{customerRegisterTime}</if>
    </set> WHERE customerId=#{customerId}
  </update>
</mapper>
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
